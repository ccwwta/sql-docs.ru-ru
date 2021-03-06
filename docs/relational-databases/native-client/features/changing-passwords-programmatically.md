---
description: Программное изменение SQL Server Native Client паролей
title: Смена пароля программным способом | Документация Майкрософт
ms.custom: ''
ms.date: 03/16/2017
ms.reviewer: ''
ms.prod: sql
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data access [SQL Server Native Client], password expiration
- SQL Server Native Client ODBC driver, passwords
- SQL Server Native Client OLE DB provider, passwords
- passwords [SQL Server], expiration
- SQLNCLI, password expiration
- expiration [SQL Server Native Client]
- passwords [SQL Server], modifying
- expired passwords [SQL Server Native Client]
- SQL Server Native Client, password expiration
- modifying passwords
ms.assetid: 624ad949-5fed-4ce5-b319-878549f9487b
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: a356ea0603d096fc339495f028b1e4f86af81f92
ms.sourcegitcommit: 1a544cf4dd2720b124c3697d1e62ae7741db757c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2020
ms.locfileid: "97463385"
---
# <a name="changing-sql-server-native-client-passwords-programmatically"></a>Программное изменение SQL Server Native Client паролей
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  В версиях, предшествующих [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], при истечении пароля пользователя переустановить его мог только администратор. Начиная с [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] , [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] собственный клиент поддерживает обработку истечения срока действия пароля программным способом с помощью [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] собственного клиентского OLE DB поставщика и [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] драйвера ODBC собственного клиента, а также путем изменения диалоговых окон **входа в SQL Server** .  
  
> [!NOTE]  
>  По возможности следует предлагать пользователям вводить свои учетные данные во время выполнения, избегая их сохранения. Если необходимо сохранить учетные данные пользователей, зашифруйте их с помощью [интерфейса API шифрования Win32](/windows/win32/seccrypto/cryptography-reference). Дополнительные сведения об использовании паролей см. в разделе [Надежные пароли](../../../relational-databases/security/strong-passwords.md).  
  
## <a name="sql-server-login-error-codes"></a>Коды ошибок имени входа SQL Server  
 Если соединение нельзя установить из-за проблем проверки подлинности, то для диагностики и восстановления приложению будет доступен один из существующих кодов ошибок SQL Server.  
  
|Код ошибки SQL Server|Сообщение об ошибке|  
|---------------------------|-------------------|  
|15113|Ошибка имени входа для пользователя "%.*ls". Причина: Ошибка проверки пароля. Учетная запись заблокирована.|  
|18463|Ошибка входа пользователя «%.*ls». Причина: ошибка изменения пароля. В данный момент этот пароль не может быть использован.|  
|18464|Ошибка входа пользователя «%.*ls». Причина: ошибка изменения пароля. Пароль слишком короткий и не отвечает требованиям политики.|  
|18465|Ошибка входа пользователя «%.*ls». Причина: ошибка изменения пароля. Пароль слишком длинный и не отвечает требованиям политики.|  
|18466|Ошибка входа пользователя «%.*ls». Причина: ошибка изменения пароля. Пароль недостаточно сложный и не отвечает требованиям политики.|  
|18467|Ошибка входа пользователя «%.*ls». Причина: ошибка изменения пароля. Пароль не отвечает требованиям динамической библиотеки фильтрации паролей.|  
|18468|Ошибка входа пользователя «%.*ls». Причина: ошибка изменения пароля. В процессе проверки пароля произошла непредвиденная ошибка.|  
|18487|Ошибка входа пользователя «%.*ls». Причина: Истек срок действия пароля для этой учетной записи.|  
|18488|Ошибка входа пользователя «%.*ls». Причина: Пароль для данной учетной записи необходимо изменить.|  
  
## <a name="sql-server-native-client-ole-db-provider"></a>Поставщик OLE DB для собственного клиента SQL Server  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента поддерживает истечение срока действия пароля, хотя пользовательский интерфейс и программный.  
  
### <a name="ole-db-user-interface-password-expiration"></a>Пользовательский интерфейс OLE DB для истечения срока действия пароля  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента поддерживает истечение срока действия пароля через изменения, внесенные в диалоговые окна **входа SQL Server** . Если свойство DBPROP_INIT_PROMPT установлено в значение DBPROMPT_NOPROMPT, то в случае истечения срока действия пароля попытка начального соединения завершится с ошибкой.  
  
 Если свойство DBPROP_INIT_PROMPT установлено в любое другое значение, диалоговое окно **Имя входа SQL Server** появится независимо от того, истек срок действия пароля или нет. Чтобы сменить пароль, пользователь может нажать кнопку **Параметры** и установить флажок **Сменить пароль**.  
  
 Если срок действия пароля истек, а пользователь нажимает кнопку "ОК", [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] предложит ему ввести и подтвердить новый пароль с помощью диалогового окна **Изменить пароль SQL Server**.  
  
#### <a name="ole-db-prompt-behavior-and-locked-accounts"></a>Поведение подсказки OLE DB и заблокированные учетные записи  
 Попытки соединения могут окончиться неудачей, если учетная запись заблокирована. В этом случае вслед за выводом диалогового окна **Имя входа SQL Server** для пользователя отображается сообщение об ошибке сервера, и попытка соединения аварийно завершается. Это может также произойти после отображения диалогового окна **Изменить пароль SQL Server**, если пользователь неправильно ввел старый пароль. В этом случае будет выведено то же сообщение об ошибке, а попытка соединения отменяется.  
  
#### <a name="ole-db-connection-pooling-password-expiration-and-locked-accounts"></a>Пул соединений OLE DB, истечение срока действия пароля и заблокированные учетные записи  
 Учетная запись может оказаться заблокированной или может истечь срок действия пароля, в то время как соединение останется активным в пуле соединений. Сервер проверяет наличие паролей с истекшим сроком действия и заблокированных учетных записей в двух случаях. Во-первых, при первоначальном создании соединения. Во-вторых, после восстановления соединения, при получении соединения из пула.  
  
 Если попытка восстановления завершилась неудачно, то соединение удаляется из пула и возвращается ошибка.  
  
### <a name="ole-db-programmatic-password-expiration"></a>Программное истечение срока действия пароля OLE DB  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента поддерживает истечение срока действия пароля с помощью добавления свойства SSPROP_AUTH_OLD_PASSWORD (типа VT_BSTR), добавленного в набор свойств DBPROPSET_SQLSERVERDBINIT.  
  
 Существующее свойство «Password» ссылается на свойство DBPROP_AUTH_PASSWORD и используется для хранения нового пароля.  
  
> [!NOTE]  
>  В строке подключения свойство «Old Password» устанавливает значение свойства SSPROP_AUTH_OLD_PASSWORD, являющееся текущим паролем (возможно, с истекшим сроком действия), недоступным через свойство строки поставщика.  
  
 Поставщик не сохраняет значение этого свойства. Когда это свойство установлено, при первом соединении поставщик не использует пул соединений, поскольку это вызовет новое соединение. Если пароль успешно изменен, текущее соединение нельзя использовать повторно, поскольку оно все еще содержит старый пароль, который будет недопустимым после изменения пароля. Кроме того, при успешном входе поставщик очистит данное свойство. Дальнейшие попытки получения старого пароля вернут значение VT_EMPTY.  
  
> [!NOTE]  
>  Свойство SSPROP_AUTH_OLD_PASSWORD не нужно сохранять, поскольку оно используется только при истечении срока действия пароля.  
  
 Обратите внимание, что при установке свойства «Old Password» поставщик предполагает, что была сделана попытка изменить пароль, если не была также указана проверка подлинности Windows, имеющая приоритет.  
  
 Если используется проверка подлинности Windows, при указании старого пароля возвращается либо DB_E_ERRORSOCCURRED, либо DB_S_ERRORSOCCURRED в зависимости от того, был ли указан старый пароль как REQUIRED или OPTIONAL соответственно, а значение состояния DBPROPSTATUS_CONFLICTINGBADVALUE возвращается в параметре *dwStatus*. Это определяется при вызове метода **IDBInitialize::Initialize**.  
  
 Если попытка смены пароля завершилась непредвиденной ошибкой, то сервер возвращает код ошибки 18468. Попытка соединения возвращает стандартный код ошибки OLEDB.  
  
 Дополнительные сведения о наборе свойств DBPROPSET_SQLSERVERDBINIT см. в статье [Свойства инициализации и авторизации](../../../relational-databases/native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).  
  
## <a name="sql-server-native-client-odbc-driver"></a>Драйвер ODBC для собственного клиента SQL Server  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента поддерживает истечение срока действия пароля, хотя пользовательский интерфейс и программный.  
  
### <a name="odbc-user-interface-password-expiration"></a>Пользовательский интерфейс ODBC истечения срока действия пароля  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента поддерживает истечение срока действия пароля через изменения, внесенные в диалоговые окна **SQL Server login** .  
  
 Если [SQLDriverConnect](../../../relational-databases/native-client-odbc-api/sqldriverconnect.md) вызывается и для параметра **DriverCompletion** задано значение SQL_DRIVER_NOPROMPT, то попытка первоначального подключения завершится неудачей, если срок действия пароля истек. При последующих вызовах **SqlError** или **SQLGETDIAGREC** возвращаются значение SQLSTATE 28000 и значение машинного кода ошибки 18487.  
  
 Если для **DriverCompletion** задано любое другое значение, пользователь видит диалоговое окно **входа SQL Server** , независимо от того, истек ли срок действия пароля. Чтобы сменить пароль, пользователь может нажать кнопку **Параметры** и установить флажок **Сменить пароль**.  
  
 Если пользователь нажмет кнопку ОК и срок действия пароля истек, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] запрашивает ввод и подтверждение нового пароля с помощью диалогового окна **изменить SQL Server пароль** .  
  
#### <a name="odbc-prompt-behavior-and-locked-accounts"></a>Поведение подсказки ODBC и заблокированные учетные записи  
 Попытки соединения могут окончиться неудачей, если учетная запись заблокирована. В этом случае вслед за выводом диалогового окна **Имя входа SQL Server** для пользователя отображается сообщение об ошибке сервера, и попытка соединения аварийно завершается. Это может также произойти после отображения диалогового окна **Изменить пароль SQL Server**, если пользователь неправильно ввел старый пароль. В этом случае будет выведено то же сообщение об ошибке, а попытка соединения отменяется.  
  
#### <a name="odbc-connection-pooling-password-expiry-and-locked-accounts"></a>Пул соединений ODBC, истечение срока действия пароля и заблокированные учетные записи  
 Учетная запись может оказаться заблокированной или может истечь срок действия пароля, в то время как соединение останется активным в пуле соединений. Сервер проверяет наличие паролей с истекшим сроком действия и заблокированных учетных записей в двух случаях. Во-первых, при первоначальном создании соединения. Во-вторых, после восстановления соединения, при получении соединения из пула.  
  
 Если попытка восстановления завершилась неудачно, то соединение удаляется из пула и возвращается ошибка.  
  
### <a name="odbc-programmatic-password-expiration"></a>Программное истечение срока действия пароля ODBC  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента поддерживает истечение срока действия пароля с помощью добавления атрибута SQL_COPT_SS_OLDPWD, который задается перед подключением к серверу с помощью функции [SQLSetConnectAttr](../../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md) .  
  
 Атрибут SQL_COPT_SS_OLDPWD дескриптора соединения ссылается на пароль с истекшим сроком действия. Для этого атрибута не существует атрибута строки соединения, поскольку это может повлиять на пул соединений. При успешном входе драйвер очищает этот атрибут.  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента возвращает SQL_ERROR в четырех случаях для этой функции: истечение срока действия пароля, конфликт политики паролей, блокировка учетной записи и при установке свойства старого пароля при использовании проверки подлинности Windows. Драйвер возвращает пользователю соответствующие сообщения об ошибках при вызове [SQLGetDiagField](../../../relational-databases/native-client-odbc-api/sqlgetdiagfield.md) .  
  
## <a name="see-also"></a>См. также:  
 [Компоненты собственного клиента SQL Server](../../../relational-databases/native-client/features/sql-server-native-client-features.md)  
  
