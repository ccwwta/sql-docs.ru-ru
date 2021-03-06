---
description: MSSQLSERVER_17890
title: MSSQLSERVER_17890
ms.custom: ''
ms.date: 12/25/2020
ms.prod: sql
ms.reviewer: ramakoni1, pijocoder, suresh-kandoth, vencher, tejasaks, docast
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 17890 (Database Engine error)
ms.assetid: ''
author: suresh-kandoth
ms.author: ramakoni
ms.openlocfilehash: 121ec18d62a79a10df015d26c0e2c2885c8cd0b5
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100340760"
---
# <a name="mssqlserver_17890"></a>MSSQLSERVER_17890
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

## <a name="details"></a>Сведения

|attribute|Значение|
|---|---|
|Название продукта|SQL Server|
|Идентификатор события|17890|
|Источник события|MSSQLSERVER|
|Компонент|SQLEngine|
|Символическое имя|SRV_WS_TRIMMED|
|Текст сообщения|Значительная часть памяти процессов SQL Server выгружена на диск. Это может привести к снижению производительности. Продолжительность: %d секунд. Рабочий набор (КБ): %I64d, зафиксировано (КБ): %I64d, использовано памяти: %d %%.|
||

## <a name="explanation"></a>Пояснение

В журнале ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или в журнале событий приложений Windows может появиться следующее сообщение об ошибке.

> Значительная часть памяти процессов SQL Server выгружена на диск. Это может привести к снижению производительности. Длительность. 0 секунд. Рабочий набор (КБ): 3383250, выделено памяти (КБ): 9112480, использование памяти: 37 %.

Кроме того, вы можете заметить внезапное замедление при выполнении запросов и любых других операциях с SQL Server.

## <a name="cause"></a>Причина

[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отслеживает различные сведения о памяти, связанные с процессом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. В этом случае обнаружено, что рабочий набор процесса занимает менее 50 % от выделенной процессу памяти. В результате отображается такое предупреждение. Типичные причины появления этого предупреждения могут быть следующими:

- Операционная система выгружает в файл подкачки большие части выделенной памяти [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].
- Это может быть связано с внезапным увеличением потребления памяти другими приложениями или самой операционной системой.
- Это также может произойти, если какие-то драйверы устройств запрашивают выделение непрерывного участка памяти для своих потребностей.

## <a name="user-action"></a>Рекомендуемые действия

Вы можете запретить операционной системе Windows выгружать на диск память буферного пула процесса [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], заблокировав выделенную для этого буферного пула часть физической памяти. Чтобы заблокировать память, назначьте право "Блокировка страниц в памяти" учетной записи пользователя, которая используется в качестве стартовой учетной записи для службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Прежде чем воплощать в жизнь это решение, ознакомьтесь с разделами [Что приводит к выгрузке на диск памяти SQL Server](#what-causes-sql-server-memory-to-be-paged-out) и "Важные аспекты, которые нужно учесть перед назначением пользователю прав на блокировку страниц в памяти" для экземпляра SQL Server.

> [!NOTE]
> Использование блокировки страниц в памяти гарантирует, что управляемая [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] память не будет выгружаться на диск. Однако стеки потоков, EXE-файлы и любые библиотеки DLL, память кучи и память CLR могут вытесняться из памяти операционной системой.
>
> Начиная с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2008 с пакетом обновления 1 (SP1) и накопительным обновлением 2, выпуски [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Standard и Enterprise поддерживают применение права пользователя на блокировку страниц в памяти. Дополнительные сведения о поддержке блокировки страниц см. в статье базы знаний [KB970070 — Поддержка заблокированных страниц в системах SQL Server Standard Edition (64-разрядных)](https://support.microsoft.com/help/970070).

Чтобы назначить право пользователя "Блокировка страниц в памяти", выполните следующие действия:

1. Нажмите кнопку **Пуск**, выберите команду **Выполнить**, введите *gpedit.msc* и щелкните **ОК**.
1. Откроется диалоговое окно "Групповая политика".
1. Последовательно разверните узлы **Конфигурация компьютера** и **Параметры Windows**.
1. Разверните узлы **Настройки безопасности** и **Локальные политики**.
1. Щелкните "Назначение прав пользователя", а затем дважды щелкните **Блокировка страниц в памяти**.
1. В диалоговом окне **Параметры локальной политики безопасности** щелкните **Добавить пользователя** или **Группа**.
1. В диалоговом окне **Выберите пользователей** или **Группы** добавьте учетную запись, у которой есть разрешение на запуск файла Sqlservr.exe, а затем щелкните **ОК**.
1. Закройте диалоговое окно **Групповая политика**.
1. Перезапустите службу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .

После того, как вы назначите пользователю право "Блокировка страниц в памяти" и перезапустите службу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], операционная система Windows не будет выгружать на диск память буферного пула в процессе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Но операционная система Windows сохранит возможность выгружать на диск память процесса [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из небуферного пула.

Чтобы убедиться в использовании этого права пользователя экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], проверьте в журнале ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] наличие следующего сообщения при запуске системы: "Для буферного пула используются блокированные страницы."

Это сообщение применимо только к SQL Server. Дополнительные сведения об этом сообщении в журнале ошибок см. в следующей статье: [Нужно ли присваивать разрешение "Блокировка страниц в памяти" в локальной системе?](https://techcommunity.microsoft.com/t5/sql-server-support/do-i-have-to-assign-the-lock-pages-in-memory-privilege-for-local/ba-p/315426)

Хотя операционная система Windows выгружает на диск память из небуферного пула, все равно могут возникать проблемы с производительностью. Но при этом в журнале ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не регистрируются сообщения об ошибках, упомянутые в разделе "Объяснение".

## <a name="what-causes-sql-server-memory-to-be-paged-out"></a>Что приводит к выгрузке на диск памяти SQL Server

Существует три основные категории проблем, которые могут вызвать такую проблему.

- Проблемы, связанные с приложением. Все приложения совокупно исчерпали доступную физическую память, поэтому операционная система вынуждена освободить некоторый объем памяти для новых запросов приложений к ресурсам. Как правило, для устранения этой причины нужно определить, какие именно приложения сильно расходуют память, и предпринять соответствующие шаги для сбалансированного распределения между ними памяти, чтобы не исчерпывать доступный объем ОЗУ.
- Проблемы с драйверами устройств. Драйверы устройств могут вызвать выгрузку на диск памяти всех процессов, если некорректно вызывают функцию выделения памяти.
- Проблемы с операционной системой.

Ниже представлены сведения по каждой из этих категорий.

- **Проблемы, связанные с приложением.** Вместе приложения могут исчерпать доступный объем ОЗУ в системе. При создании новых запросов на выделение памяти операционная система пытается удовлетворить их, а если свободной памяти нет, для ее освобождения она сократит рабочий набор уже выполняемых приложений. В таких случаях можно заметить значительное сокращение рабочего набора для всех или многих приложений сразу. Чтобы отследить это, реализуйте сбор данных с помощью следующего счетчика Монитора производительности для всех приложений в системе:

  - Объект производительности: Процесс
  - Счетчик: Рабочий набор
  
  Кроме того, отслеживайте следующий счетчик для сопоставления объема доступной в системе физической памяти.
  
  - Объект производительности: Память
  - Счетчик: Объем доступной памяти (МБ)
  
  Типичное поведение, которое вы можете здесь наблюдать, — это снижение объема доступной памяти почти до 0 МБ с последующим резким снижением значений счетчиков рабочего набора для большинства (или всех) процессов в системе. В такой ситуации следует предпринять какие-то действия для снижения использования памяти в системе, например уменьшить максимальный объем памяти (Max Server Memory) для SQL Server.
  
    Также может оказаться, что приложения слишком активно используют системный кэш, что приводит к увеличению размера системного кэша. В ответ на рост системного кэша операционная система выгружает на диск рабочий набор процесса [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или других приложений. При возникновении этой проблемы можно применить некоторые функции управления памятью в приложении. Эти функции управляют пространством системного кэша, которое доступно операциям файлового ввода-вывода в приложении. Например, функции SetSystemFileCacheSize и GetSystemFileCacheSize можно использовать для управления пространством системного кэша, которое доступно операциям файлового ввода-вывода.
  
    Объект производительности "Память" содержит несколько счетчиков, значения которых помогают определить, использует ли рабочий набор системного кэша чрезмерно много памяти. Сюда относятся, например, счетчики "Байт кэш-памяти" и "Резидентных байт системного кэша". Дополнительные сведения на эту тему см. в следующих документах:
  
    - [Слишком большой объем кэша](/archive/blogs/ntdebugging/too-much-cache)
    - [Служба динамических кэшей Microsoft Windows](/archive/blogs/ntdebugging/microsoft-windows-dynamic-cache-service)
    - [В приложениях и службах возникают проблемы с производительностью, когда системный кэш файлов занимает большую часть физической памяти.](https://support.microsoft.com/help/976618)
  
    Вы можете скачать и развернуть службу динамического кэша Microsoft Windows, чтобы управлять объемом памяти, потребляемым системным кэшем.

- **Проблемы с драйверами устройств.** Если драйвер устройства использует функцию `MmAllocateContiguousMemory` и устанавливает для параметра HighestAcceptableAddress значение менее 4 ГБ, то операционная система Windows может выгрузить на диск рабочий набор любого процесса в системе, включая процесс [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Чтобы устранить эту проблему, обратитесь к поставщику драйвера устройства за обновлением драйвера.

    Когда драйвер устройства пытается выделить память, операционная система Windows может выгружать на диск рабочие наборы других приложений. Это исправление для Windows позволяет с помощью трассировки событий найти проблемный драйвер устройства. Дополнительные сведения о поиске драйвера, который вызывает сокращение рабочего набора, см. в статье [Определение драйверов, выделяющих непрерывную память](/previous-versions/windows/desktop/xperf/identifying-drivers-that-allocate-contiguous-memory).

- **Проблемы операционной системы.** Чтобы устранить некоторые известные проблемы, из-за которых операционная система Windows выгружает на диск рабочий набор процесса [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], примените исправления, описанные в приведенных ниже статьях базы знаний Майкрософт.

  > [!NOTE]
  > Все эти исправления являются накопительными. Более поздние версии исправления содержат все более ранние версии того же исправления.

  - Набор [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может уменьшаться, если система использует некоторые расширенные возможности TCP. Дополнительные сведения см. в статье [Устранение неполадок с расширенными функциями производительности сети, такими как RSS и NetDMA](/troubleshoot/windows-server/networking/troubleshoot-network-performance-features-rss-netdma).

  - Если вы выполняете [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в Windows Server 2008, необходимо применить все исправления для известных проблем, которые могут приводить к уменьшению рабочего набора или чрезмерному потреблению памяти другими компонентами операционной системы. Дополнительные сведения см. в статье [Процесс создания отчета может перестать отвечать на запросы при запуске Perfmon.exe с шаблоном диагностики Active Directory для создания отчета на контроллере домена под управлением Windows Server 2008](/troubleshoot/windows-server/performance/report-generation-process-stops-responding).

  - Если вы выполняете [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в Windows Server 2008 R2, необходимо применить исправления для известных проблем, которые могут приводить к уменьшению рабочего набора. Дополнительные сведения см. в следующих статьях:

    - [Компьютер под управлением Windows 7 или Windows Server 2008 R2 перестает отвечать при запуске большого приложения](https://support.microsoft.com/help/979149)
    - [Низкая производительность на компьютере с процессорами на основе NUMA и под управлением Windows Server 2008 R2 или Windows 7, если поток запрашивает много памяти в пределах первых 4 ГБ памяти](https://support.microsoft.com/help/2155311)
    - [Компьютер периодически работает медленно или прекращает работу, если в Windows Server 2008 R2 используется драйвер Storport](https://support.microsoft.com/help/2468345)

## <a name="important-considerations-before-you-assign-the-lock-pages-in-memory-user-right"></a>Важные аспекты, которые нужно учесть перед назначением пользователю прав на блокировку страниц в памяти

Прежде чем назначить пользователю право "Блокировка страниц в памяти", необходимо учесть дополнительные рекомендации. Если назначить это право пользователя в неправильно настроенных системах, они могут стать нестабильными или существенно снизится их производительность. Кроме того, в журнале событий начнет появляться событие с идентификатором 333.

Если вы обратитесь в службу поддержки пользователей Майкрософт (CSS) с жалобой на эту проблему, инженеры CSS могут предложить вам отозвать это право пользователя для учетной записи, которая используется в качестве стартовой учетной записи для службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Этот шаг иногда требуется для получения важных данных о производительности, которые помогут инженерам CSS найти правильную конфигурацию параметров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и других приложений, работающих в системе. Когда инженеры CSS завершат сбор данных о производительности, вы сможете снова назначить право "Блокировка страниц в памяти" стартовой учетной записи для службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].

Прежде чем присвоить право пользователя "Блокировка страниц в памяти", включите сбор данных для журнала Монитора производительности, чтобы оценить требования к памяти для приложений и служб, установленных в системе. К этим приложениям относится и SQL Server. Чтобы определить требования к памяти, собирайте следующие базовые сведения.

- Убедитесь, что параметры максимального и минимального объема памяти сервера настроены правильно. Эти параметры отражают требования к памяти только для буферного пула процесса [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. В них не включается память, выделяемая для других компонентов в процессе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. К этим компонентам относятся:

  - рабочие потоки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)];
  - библиотеки DLL и компоненты, которые процесс [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] загружает в адресное пространство процесса [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)];
  - операции резервного копирования и восстановления.

- К библиотекам DLL и компонентам относятся всевозможные поставщики OLE DB, расширенные хранимые процедуры, объекты Microsoft COM для хранимой процедуры sp_OACreate, связанных серверов и среды CLR [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Выделяемая для этих компонентов память помещается в область из небуферного пула, из адресного пространства процесса [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Чтобы правильно определить максимальный общий объем памяти, который может использовать процесс [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], необходимо вычесть выделенную для компонентов память небуферного пула из общего объема памяти, который должен использовать процесс [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Полученное значение остатка следует указать как значение параметра максимального объема памяти сервера. Прежде чем настраивать параметры максимального и минимального объема памяти сервера, внимательно изучите раздел "Настройка параметров памяти вручную" в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].

- Определите требования к памяти для других приложений и компонентов операционной системы Windows. Приложения могут содержать дополнительные компоненты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], например агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], агенты репликации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Reporting Services, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Analysis Services, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services и полнотекстовый поиск [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Приложения, которые выполняют операции резервного копирования и копирования файлов, могут использовать большой объем памяти. Оцените такие операции, как массовое копирование и действия агента моментальных снимков, которые создают значительную нагрузку файлового ввода и вывода. Требования к памяти для всех этих приложений необходимо учитывать при определении значений параметров максимального и минимального объема памяти сервера. Чтобы определить требования к памяти для каждого процесса, можно использовать счетчики Private Bytes и Working Set из объекта Process для конкретного процесса.

- По умолчанию право "Блокировка страниц в памяти" уже назначено встроенной учетной записи Local System. Дополнительные сведения см. в следующем разделе веб-сайта Майкрософт: [Нужно ли присваивать разрешение "Блокировка страниц в памяти" в локальной системе?](https://techcommunity.microsoft.com/t5/sql-server-support/do-i-have-to-assign-the-lock-pages-in-memory-privilege-for-local/ba-p/315426?advanced=false&collapse_discussion=true&search_type=thread)

- Если одна учетная запись пользователя Windows используется глобально для всех процессов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в домене, определите права пользователя, предоставленные ей групповой политикой. 32-разрядный процесс [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может использовать эту учетную запись в качестве стартовой учетной записи. Но этой учетной записи право пользователя "Блокировка страниц в памяти" требуется для использования функции `Address Windowing Extensions` (AWE). Дополнительные сведения см. в разделе "Выделение максимального объема памяти для SQL Server" электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].

- Прежде чем настраивать параметры максимального и минимального объема памяти сервера для нескольких экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], изучите требования к памяти небуферного пула для каждого экземпляра SQL Server. Затем настройте эти параметры для каждого экземпляра SQL Server.

В идеале базовые сведения следует собирать во время пиковых нагрузок. Это позволит определить требования к памяти для различных приложений и компонентов, соответствующую максимальной загрузке системы. Требования к памяти могут быть разными для разных систем в зависимости от выполняемых действий и приложений. Вы можете запросить сведения, предоставленные в динамическом административном представлении sys.dm_os_process_memory, чтобы определить, сталкивается ли система с нехваткой памяти. Дополнительные сведения см. в статье [sys.dm_os_process_memory (Transact-SQL)](../system-dynamic-management-views/sys-dm-os-process-memory-transact-sql.md).

## <a name="improvements-added-in-windows-server-2008-and-r2-version"></a>Улучшения, добавленные в версии Windows Server 2008 и R2

В Windows Server 2008 и Windows Server 2008 R2 улучшен механизм выделения непрерывной памяти. Это улучшение позволяет Windows Server 2008 и Windows Server 2008 R2 до определенной степени сократить число проблем с выгрузкой на диск рабочего множества приложений при поступлении новых запросов на выделение памяти.

Ниже приведено пояснение к этим улучшениям, которое содержится в техническом документе Майкрософт "Усовершенствование управления памятью в Windows".

*В Windows Server 2008 существенно улучшено выделение непрерывной физической памяти. Запросы на выделение непрерывной памяти гораздо чаще будут выполняться успешно, так как диспетчер памяти теперь динамически заменяет страницы, обычно без усечения рабочего набора и операций ввода-вывода. Кроме того, теперь намного больше типов страниц (например, стеки ядра и страницы метаданных файловой системы) назначаются кандидатами на замену. Следовательно, в любой момент времени доступно больше непрерывной памяти. Кроме того, значительно сокращаются затраты на получение таких выделений.*

Дополнительные сведения см. в статье [Проблемы SQL Server с усечением рабочего набора](https://techcommunity.microsoft.com/t5/sql-server-support/sql-server-working-set-trim-problems-consider/ba-p/315462?advanced=false&collapse_discussion=true&search_type=thread).

Продукты сторонних производителей, обсуждаемые в этой статье, разрабатываются компаниями, независимыми от корпорации Майкрософт. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно производительности или надежности таких продуктов.