---
title: Объединение подключений в пул в SQL Server
description: Узнайте, как поставщик данных Microsoft SqlClient для SQL Server позволяет избежать затрат на новые подключения благодаря пулу подключений к SQL Server.
ms.date: 11/13/2020
dev_langs:
- csharp
ms.assetid: 7e51d44e-7c4e-4040-9332-f0190fe36f07
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.topic: conceptual
author: David-Engel
ms.author: v-daenge
ms.reviewer: v-chmalh
ms.openlocfilehash: 9538368cdcc39d3a037c609fc79f65d5d3cb8e45
ms.sourcegitcommit: d8cdbb719916805037a9167ac4e964abb89c3909
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/20/2021
ms.locfileid: "98596379"
---
# <a name="sql-server-connection-pooling-adonet"></a>Пул подключений к SQL Server (ADO.NET)

[!INCLUDE[appliesto-netfx-netcore-netst-md](../../includes/appliesto-netfx-netcore-netst-md.md)]

[!INCLUDE[Driver_ADONET_Download](../../includes/driver_adonet_download.md)]

Соединение с сервером базы данных обычно состоит из нескольких длительных шагов. Необходимо установить физический канал, например сокет или именованный канал, выполнить первоначальное подтверждение установления связи с сервером, выполнить синтаксический анализ данных строки соединения, сервер должен проверить подлинность соединения, а также запустить проверку прикреплений в текущей транзакции и т. д.

На практике большинство приложений использует только одно или несколько различных конфигураций соединений. Это означает, что во время выполнения приложения многие идентичные соединения будут повторно открываться и закрываться. Чтобы минимизировать расходы на открытие подключений, поставщик данных Microsoft SqlClient для SQL Server использует методику оптимизации, известную как *пул подключений*.

Пул соединений снижает количество открытий новых соединений. *Владелец пула* поддерживает управление физическим подключением. Он управляет соединениями с помощью поддержания набора активных соединений для каждой конфигурации данного соединения. Каждый раз, когда пользователь вызывает метод `Open` в соединении, организатор пулов ищет в пуле доступное соединение. Если соединение пула доступно, вместо открытия нового соединения он возвращает его участнику. При вызове приложением метода `Close` в соединении вместо закрытия организатор пулов возвращает его в набор активных соединений пула. После возвращения соединения в пул оно готово к повторному использованию при следующем вызове метода `Open`.

В пул могут помещаться только соединения с одинаковой конфигурацией. Поставщик данных Microsoft SqlClient для SQL Server поддерживает одновременно несколько пулов, по одному для каждой конфигурации. Соединения разделяются в пулы строкой соединения, а при использовании встроенной безопасности - удостоверением Windows. Соединения также заносятся в пул в зависимости от того, прикреплены ли они к транзакции. При использовании метода <xref:Microsoft.Data.SqlClient.SqlConnection.ChangePassword%2A> экземпляр <xref:Microsoft.Data.SqlClient.SqlCredential> влияет на пул соединений. Различные экземпляры <xref:Microsoft.Data.SqlClient.SqlCredential> используют различные пулы соединений, даже если идентификатор пользователя и пароль совпадают.

Организация пулов соединений может существенно улучшить производительность и масштабируемость приложения. По умолчанию в поставщике данных Microsoft SqlClient для SQL Server включена поддержка пулов подключений. Пока организатор пулов не будет явно отключен, он оптимизирует соединения по мере их открытия и закрытия в приложении. Также можно указать несколько модификаторов строки соединения для управления поведением пула соединений. Дополнительные сведения см. в разделе **Управление пулами подключений с помощью ключевых слов строки подключения** далее в этой статье.

> [!IMPORTANT]
> Если пулы подключений включены, то при истечении времени ожидания и любой другой ошибке входа создается исключение. Последующие попытки подключения завершаются сбоем в течение периода `blocking period` длительностью **5** секунд. Если приложение пытается установить подключение в течение интервала блокирования, то снова выдается первое исключение. Новые сбои после периода блокировки будут вызывать новые периоды блокировки, каждый из которых будет в два раза больше предыдущего, вплоть до *максимального периода в **1** минуту*.

> [!NOTE]
> Механизм `blocking period`по умолчанию не применяется к Azure SQL Server. Это поведение можно изменить через свойство <xref:Microsoft.Data.SqlClient.PoolBlockingPeriod> в <xref:Microsoft.Data.SqlClient.SqlConnection.ConnectionString>, но только не для *.NET Standard*.

## <a name="pool-creation-and-assignment"></a>Создание и назначение пула

При первом открытии соединения создается пул соединений, основанный на алгоритме точного совпадения, связанного с пулом строкой соединения. Каждый пул соединений связывается с отдельной строкой соединения. При открытии нового соединения, если строка соединения не соответствует в точности существующему пулу, создается новый пул.

> [!NOTE]
> Подключения объединяются в пулы по _процессам_, _доменам приложения_, _строкам подключения_, а если используется встроенная безопасность, то и по _удостоверениям Windows_. Строки соединения должны точно совпадать. Ключевые слова, указанные в различном порядке для одного соединения, будут включены в пул по отдельности.

> [!NOTE]
> Если аргумент `MinPoolSize` не указан в строке соединения или указано значение 0, соединения в пуле будут закрыты после периода отсутствия активности. Однако, если значение аргумента `MinPoolSize` больше 0, пул соединений не уничтожается, пока не будет выгружен домен приложения `AppDomain` и не завершится процесс. Обслуживание неактивных или пустых пулов требует минимальных системных издержек.

> [!NOTE]
> Пул автоматически очищается при возникновении неустранимой ошибки, например переходе на другой ресурс.

В следующем примере C# создаются три новых объекта <xref:Microsoft.Data.SqlClient.SqlConnection>, но для управления ими требуется только два пула соединений. Обратите внимание, что первая и вторая строки соединения отличаются значениями, присвоенными аргументу `Initial Catalog`.  


[!code-csharp[SqlConnection_Pooling#1](~/../sqlclient/doc/samples/SqlConnection_Pooling.cs#1)]

## <a name="add-connections"></a>Добавление подключений

Пул соединений создается для каждой уникальной строки соединения. При создании пула создается множество объектов соединения, которые добавляются в пул для удовлетворения требования к минимальному размеру пула. Подключения добавляются в пул по мере необходимости, пока не будет достигнут его максимальный размер (**по умолчанию это 100 подключений**). Соединения освобождаются обратно в пул при закрытии или ликвидации.

При запросе объекта <xref:Microsoft.Data.SqlClient.SqlConnection> он получается из пула при наличии готового к использованию соединения. Чтобы соединение можно было использовать, оно не должно использоваться, иметь совпадающий контекст транзакции либо не иметь связи с каким-либо контекстом транзакций и иметь допустимую ссылку на сервер.

Организатор пулов соединений обрабатывает запросы соединений путем их повторного размещения после возврата в пул. Если достигнут максимальный размер пула, а пригодные соединения недоступны, запрос помещается в очередь. Затем владелец пула пытается получить свободное подключение, пока не истечет период ожидания (**по умолчанию это 15 секунд**). Если организатор пулов не может обработать запрос до истечения времени ожидания соединения, возникнет исключение.

> [!CAUTION]
> Настоятельно рекомендуется всегда закрывать соединение после его использования, чтобы оно вернулось в пул. Это можно сделать с помощью методов `Close` или `Dispose` объекта `Connection`, либо открывая все подключения внутри инструкции `using` (C#) или `Using` (Visual Basic). Соединения, которые явно не закрыты, нельзя добавить или вернуть в пул. Дополнительные сведения см. в документации по [оператору using](/dotnet/csharp/language-reference/keywords/using-statement) или в [практическом руководстве по удалению системного ресурса](/dotnet/visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource) для Visual Basic.

> [!NOTE]
> В методе `Close` вашего класса нельзя вызывать методы `Dispose` или `Connection` объектов `DataReader`, `Finalize` или любого другого управляемого объекта. В методе завершения следует только освобождать неуправляемые ресурсы, которыми ваш класс непосредственно владеет. Если класс не владеет какими-либо неуправляемыми ресурсами, не включайте в его определение метод `Finalize`. Дополнительные сведения см. в статье [Сборка мусора](/dotnet/standard/garbage-collection/index).

Дополнительные сведения о событиях, связанных с открытием и закрытием подключений, вы найдете в разделах документации по SQL Server: [Audit Login, класс событий](../../relational-databases/event-classes/audit-login-event-class.md) и [Audit Logout, класс событий](../../relational-databases/event-classes/audit-logout-event-class.md).

## <a name="remove-connections"></a>Удаление подключений

Владелец пулов подключений удаляет из пула подключения, которые остаются неактивными в течение **4–8** минут или теряют соединение с сервером.

> [!NOTE]
> Иногда проблемы с подключением обнаруживаются только при попытке связаться с сервером. При обнаружении соединения, которое больше не имеет связи с сервером, оно помечается как недействительное. Недействительные соединения удаляются из пула соединений только после их закрытия или возврата.

Если существующее соединение с сервером исчезло, оно может быть удалено из пула, даже если организатор пулов соединений не определил разорванное соединение и не пометил его как недопустимое. Это происходит вследствие того, что проверка соединения на допустимость уничтожит преимущества существования организатора пулов, став причиной вызова очередного цикла приема-передачи с сервером. В этом случае первая попытка использовать соединение определит его разрыв и вызовет исключение.

## <a name="clear-the-pool"></a>Очистка пула

Поставщик данных Microsoft SqlClient для SQL Server представил два новых метода для очистки пулов: <xref:Microsoft.Data.SqlClient.SqlConnection.ClearAllPools%2A> и <xref:Microsoft.Data.SqlClient.SqlConnection.ClearPool%2A>. Метод `ClearAllPools` очищает пулы соединений данного поставщика, а метод `ClearPool` - пул, связанный с конкретным соединением.

> [!NOTE]
> Если во время вызова методов соединения использовались, они соответствующим образом помечаются. При их закрытии вместо возвращения в пул они удаляются.

## <a name="transaction-support"></a>Поддержка транзакций

Соединения выбираются из пула и назначаются в зависимости от контекста транзакции. Если в строке соединения не указан аргумент `Enlist=false`, пул соединений гарантирует прикрепление соединения к контексту <xref:System.Transactions.Transaction.Current%2A>. После закрытия и возврата соединения в пул с прикрепленной транзакцией `System.Transactions` оно резервируется таким образом, что следующий запрос к пулу соединений с той же транзакцией `System.Transactions` вернет это соединение, если оно доступно. Если при выдаче такого запроса в пуле нет доступных соединений, соединение берется и прикрепляется из части пула, не использующей транзакции. Если доступных соединений нет во всех частях пула, создается и прикрепляется новое соединение.

При закрытии соединения оно освобождается обратно в пул и в соответствующий подраздел в зависимости от его контекста транзакции. Поэтому можно закрыть соединение без создания ошибки, даже если распределенная транзакция все еще находится в ожидании. Это позволит зафиксировать или отменить распределенную транзакцию позже.

## <a name="control-connection-pooling-with-connection-string-keywords"></a>Управление пулами подключений с помощью ключевых слов строк подключений

Свойство `ConnectionString` объекта <xref:Microsoft.Data.SqlClient.SqlConnection> поддерживает пары «ключ-значение» из строки соединения, с помощью которых можно изменять логику организации пулов соединений. Для получения дополнительной информации см. <xref:Microsoft.Data.SqlClient.SqlConnection.ConnectionString%2A>.

## <a name="pool-fragmentation"></a>Фрагментация пулов

Фрагментация пула является распространенной проблемой для многих веб-приложений, в которых может создаваться большое количество пулов, которые не освобождаются, пока существует процесс. Это оставляет большое количество соединений открытыми и потребляющими память, что приводит к ухудшению производительности.

### <a name="pool-fragmentation-due-to-integrated-security"></a>Фрагментация пулов из-за встроенной безопасности

Соединения заносятся в пул в соответствии со строкой соединения, а также удостоверением пользователя. Таким образом, при использовании на веб-узле обычной проверки подлинности или проверки подлинности Windows, а также встроенной безопасности имени входа получается один пул на пользователя. Несмотря на то, что это улучшает производительность последующих запросов пользователя к базе данных, для него недоступны преимущества соединений, установленных другими пользователями. Это также приводит по крайней мере к одному соединению с сервером базы данных для каждого пользователя. Это является побочным эффектом данной архитектуры веб-приложений, который разработчики должны соизмерить с требованиями безопасности и аудита.

### <a name="pool-fragmentation-due-to-many-databases"></a>Фрагментация пулов из-за большого числа баз данных

Многие поставщики услуг Интернет размещают несколько веб-узлов на одиночном сервере. Они могут использовать одну базу данных для подтверждения проверки подлинности имени входа с помощью форм и затем открывать соединение с определенной базой данных для этого пользователя или группы пользователей. Соединение с базой данных проверки подлинности заносится в пул и используется всеми. Однако для каждой базы данных существует отдельный пул соединений, увеличивающий количество соединений с сервером.

Это также является побочным эффектом конструкции приложений. При соединении с SQL Server существует относительно простой способ устранения этого побочного эффекта без нарушения безопасности. Вместо соединения каждого пользователя или группы с отдельной базой данных устанавливается соединение с одной базой данных на сервере, а затем выполняется инструкция Transact-SQL USE, чтобы переключиться на требуемую базу данных.
 
Следующий фрагмент кода демонстрирует создание первоначального соединения с базой данных `master` и последующее переключение на требуемую базу данных, указанную в строковой переменной `databaseName`.

[!code-csharp[SqlConnection_Pooling_Use_Statement#1](~/../sqlclient/doc/samples/SqlConnection_Pooling_Use_Statement.cs#1)]

## <a name="application-roles-and-connection-pooling"></a>Роли приложений и пулы подключений

После активации роли приложения SQL Server с помощью вызова системной хранимой процедуры `sp_setapprole` контекст безопасности данного соединения сбросить нельзя. Однако, если использование пула включено, соединение возвращается в пул и при повторном использовании соединения возникает ошибка.

### <a name="application-role-alternatives"></a>Альтернативы ролям приложений

Рекомендуется пользоваться преимуществом новых механизмов безопасности, которые пришли на смену ролям приложения.

## <a name="see-also"></a>См. также

- [Организация пулов соединений](connection-pooling.md)
- [SQL Server и ADO.NET](./sql/index.md)
- [Счетчики производительности в SqlClient](performance-counters.md)
- [Microsoft ADO.NET для SQL Server](microsoft-ado-net-sql-server.md)