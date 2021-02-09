---
title: Azure Active Directory
description: Узнайте, как использовать проверку подлинности Azure Active Directory с драйверами Майкрософт для PHP для SQL Server.
ms.date: 01/29/2021
ms.prod: sql
ms.prod_service: connectivity
ms.custom: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- azure active directory, authentication, access token
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: ae3e734dee5f8ac46de2646cca9c37a7ed7748df
ms.sourcegitcommit: f30b5f61c514437ea58acc5769359c33255b85b5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2021
ms.locfileid: "99076962"
---
# <a name="connect-using-azure-active-directory-authentication"></a>Подключение с использованием проверки подлинности Azure Active Directory
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

[Azure Active Directory](/azure/active-directory/active-directory-whatis) (Azure AD) — это центральная технология управления идентификаторами пользователей, которая действует в качестве альтернативы [проверки подлинности SQL Server](how-to-connect-using-sql-server-authentication.md). Azure AD разрешает подключения к Базе данных SQL Microsoft Azure и Azure Synapse Analytics с помощью федеративных удостоверений в Azure AD с использованием имени пользователя и пароля, встроенной проверки подлинности Windows или маркера доступа Azure AD. Драйверы PHP для SQL Server предоставляют частичную поддержку этих функций.

Чтобы использовать Azure AD, используйте ключевые слова **Authentication** или **AccessToken** (они являются взаимоисключающими), как показано в следующей таблице. Дополнительные технические сведения см. в статье [Using Azure Active Directory with the ODBC Driver](../odbc/using-azure-active-directory.md) (Использование Azure Active Directory с драйвером ODBC).

|Ключевое слово|Значения|Описание|
|-|-|-|
|**AccessToken**|Не задано (по умолчанию).|Режим проверки подлинности определяется другими ключевыми словами. Дополнительные сведения см. в статье [Connection Options](connection-options.md). |
||Байтовая строка|Маркер доступа Azure AD, извлеченный из ответа OAuth JSON. Строка подключения не должна содержать идентификатор пользователя, пароль или ключевое слово Authentication (требуется драйвер ODBC версии 17 или более поздней версии в Linux или macOS). |
|**Аутентификация**|Не задано (по умолчанию).|Режим проверки подлинности определяется другими ключевыми словами. Дополнительные сведения см. в статье [Connection Options](connection-options.md). |
||`SqlPassword`|Прямая проверка подлинности в экземпляре SQL Server (может быть экземпляром Azure) по имени пользователя и паролю. Имя пользователя и пароль необходимо передать в строку подключения с использованием ключевых слов **UID** и **PWD**. |
||`ActiveDirectoryPassword`|Проверка подлинности по удостоверению Azure Active Directory с использованием имени пользователя и пароля. Имя пользователя и пароль необходимо передать в строку подключения с использованием ключевых слов **UID** и **PWD**. |
||`ActiveDirectoryMsi`|Проверка подлинности с помощью управляемого удостоверения, назначаемого системой или пользователем (требуется драйвер ODBC версии 17.3.1.1 или более поздней версии). Общие сведения и учебники см. в статье [Что такое управляемые удостоверения для ресурсов Azure?](/azure/active-directory/managed-identities-azure-resources/overview).|
||`ActiveDirectoryServicePrincipal`|Проверка подлинности с помощью объектов субъекта-службы (требуется ODBC Driver версии 17.7 или более поздней). Дополнительные сведения и примеры см. в статье [Объекты приложения и субъекта-службы в Azure Active Directory](/azure/active-directory/develop/app-objects-and-service-principals).|

Ключевое слово **Authentication** влияет на параметры безопасности подключения. Если оно задано в строке подключения, по умолчанию для ключевого слова **Encrypt** указано значение true, то есть клиент будет запрашивать шифрование. Кроме того, сертификат сервера будет проверяться независимо от параметра шифрования, если для параметра **TrustServerCertificate** установлено значение true (**false** по умолчанию). Эта функция отличается от старого, менее безопасного метода входа в систему, при котором сертификат сервера проверяется только в том случае, если шифрование запрашивается в строке подключения.

#### <a name="limitations"></a>Ограничения

В Windows базовый драйвер ODBC поддерживает еще одно значение для ключевого слова **Authentication** — **ActiveDirectoryIntegrated**, но драйверы PHP не поддерживают это значение в любой платформе.

## <a name="example---connect-using-sqlpassword-and-activedirectorypassword"></a>Пример: подключение с использованием SqlPassword и ActiveDirectoryPassword

```php
<?php
// First connect to a local SQL Server instance by setting Authentication to SqlPassword
$serverName = "myserver.mydomain";

$connectionInfo = array("UID"=>$myusername, "PWD"=>$mypassword, "Authentication"=>'SqlPassword');

$conn = sqlsrv_connect($serverName, $connectionInfo);
if ($conn === false) {
    echo "Could not connect with Authentication=SqlPassword.\n";
    print_r(sqlsrv_errors());
} else {
    echo "Connected successfully with Authentication=SqlPassword.\n";
    sqlsrv_close($conn);
}

// Now connect to an Azure SQL database by setting Authentication to ActiveDirectoryPassword
$azureServer = "myazureserver.database.windows.net";
$azureDatabase = "myazuredatabase";
$azureUsername = "myuid";
$azurePassword = "mypassword";
$connectionInfo = array("Database"=>$azureDatabase,
                        "UID"=>$azureUsername,
                        "PWD"=>$azurePassword,
                        "Authentication"=>'ActiveDirectoryPassword');

$conn = sqlsrv_connect($azureServer, $connectionInfo);
if ($conn === false) {
    echo "Could not connect with Authentication=ActiveDirectoryPassword.\n";
    print_r(sqlsrv_errors());
} else {
    echo "Connected successfully with Authentication=ActiveDirectoryPassword.\n";
    sqlsrv_close($conn);
}

?>
```

## <a name="example---connect-using-the-pdo_sqlsrv-driver"></a>Пример: подключение с использованием драйвера PDO_SQLSRV

```php
<?php
// First connect to a local SQL Server instance by setting Authentication to SqlPassword
$serverName = "myserver.mydomain";

$connectionInfo = "Database = $databaseName; Authentication = SqlPassword;";

try {
    $conn = new PDO("sqlsrv:server = $serverName ; $connectionInfo", $myusername, $mypassword);
    echo "Connected successfully with Authentication=SqlPassword.\n";
    $conn = null;
} catch (PDOException $e) {
    echo "Could not connect with Authentication=SqlPassword.\n";
    print_r($e->getMessage());
    echo "\n";
}

// Now connect to an Azure SQL database by setting Authentication to ActiveDirectoryPassword
$azureServer = "myazureserver.database.windows.net";
$azureDatabase = "myazuredatabase";
$azureUsername = "myuid";
$azurePassword = "mypassword";
$connectionInfo = "Database = $azureDatabase; Authentication = ActiveDirectoryPassword;";

try {
    $conn = new PDO("sqlsrv:server = $azureServer ; $connectionInfo", $azureUsername, $azurePassword);
    echo "Connected successfully with Authentication=ActiveDirectoryPassword.\n";
    unset($conn);
} catch (PDOException $e) {
    echo "Could not connect with Authentication=ActiveDirectoryPassword.\n";
    print_r($e->getMessage());
    echo "\n";
}
?>
```

## <a name="example---connect-using-azure-ad-access-token"></a>Пример: подключение с использованием маркера доступа Azure AD

### <a name="sqlsrv-driver"></a>Драйвер SQLSRV

```php
<?php
// Using an access token to connect: do not use UID or PWD connection options
// Assume $accToken is the valid byte string extracted from an OAuth JSON response
$connectionInfo = array("Database"=>$azureAdDatabase, "AccessToken"=>$accToken);
$conn = sqlsrv_connect($azureAdServer, $connectionInfo);
if ($conn === false) {
    echo "Could not connect with Azure AD Access Token.\n";
    print_r(sqlsrv_errors());
} else {
    echo "Connected successfully with Azure AD Access Token.\n";
    sqlsrv_close($conn);
}
?>
```

### <a name="pdo_sqlsrv-driver"></a>Драйвер PDO_SQLSRV

```php
<?php
try {
    // Using an access token to connect: do not pass in $uid or $pwd
    // Assume $accToken is the valid byte string extracted from an OAuth JSON response
    $connectionInfo = "Database = $azureAdDatabase; AccessToken = $accToken;";
    $conn = new PDO("sqlsrv:server = $azureAdServer; $connectionInfo");
    echo "Connected successfully with Azure AD Access Token\n";
    unset($conn);
} catch (PDOException $e) {
    echo "Could not connect with Azure AD Access Token.\n";
    print_r($e->getMessage());
    echo "\n";
}
?>
```

## <a name="example---connect-using-managed-identities-for-azure-resources"></a>Пример: подключение с использованием управляемых удостоверений для ресурсов Azure

### <a name="using-the-system-assigned-managed-identity-with-sqlsrv-driver"></a>Использование управляемого удостоверения, назначаемого системой, с драйвером SQLSRV

При подключении с использованием управляемого удостоверения, назначаемого системой, не указывайте параметры UID или PWD.

```php
<?php

$azureServer = 'myazureserver.database.windows.net';
$azureDatabase = 'myazuredatabase';
$connectionInfo = array('Database'=>$azureDatabase,
                        'Authentication'=>'ActiveDirectoryMsi');
$conn = sqlsrv_connect($azureServer, $connectionInfo);

if ($conn === false) {
    echo "Could not connect with Authentication=ActiveDirectoryMsi (system-assigned).\n";
    print_r(sqlsrv_errors());
} else {
    echo "Connected successfully with Authentication=ActiveDirectoryMsi (system-assigned).\n";
    
    $tsql = "SELECT @@Version AS SQL_VERSION";
    $stmt = sqlsrv_query($conn, $tsql);
    if ($stmt === false) {
        echo "Failed to run the simple query (system-assigned).\n";
        print_r(sqlsrv_errors());
    } else {
        while ($row = sqlsrv_fetch_array($stmt, SQLSRV_FETCH_ASSOC)) {
            echo $row['SQL_VERSION'] . PHP_EOL;
        }

        sqlsrv_free_stmt($stmt);
    }
    
    sqlsrv_close($conn);
}
?>
```

### <a name="using-the-user-assigned-managed-identity-with-pdo_sqlsrv-driver"></a>Использование управляемого удостоверения, назначаемого пользователем, с драйвером PDO_SQLSRV

Назначаемое пользователем управляемое удостоверение создается как изолированный ресурс Azure. Azure создает удостоверение в доверенном клиенте Azure AD используемой подписки. После создания удостоверения оно может быть назначено одному или нескольким экземплярам служб Azure. Скопируйте `Object ID` этого удостоверения и укажите его в качестве имени пользователя в строке подключения. 

Поэтому при подключении с помощью управляемого удостоверения, назначаемого пользователем, укажите идентификатор объекта в качестве имени пользователя, но не указывайте пароль.

```php
<?php

$azureServer = 'myazureserver.database.windows.net';
$azureDatabase = 'myazuredatabase';
$azureUser = '2d68f56e-9547-4dae-aee8-f3g28ab9674x';    // Object ID of the identity
$connectionInfo = "Database = $azureDatabase; Authentication = ActiveDirectoryMsi;";

try {
    $conn = new PDO("sqlsrv:server = $azureServer; $connectionInfo", $azureUser);
    echo "Connected successfully with Authentication=ActiveDirectoryMsi (user-assigned).\n";
    
    $tsql = "SELECT @@Version AS SQL_VERSION";
    
    try {
        $stmt = $conn->query($tsql);
        $result = $stmt->fetchall(PDO::FETCH_ASSOC);
        print_r($result);

        unset($stmt);
    } catch (PDOException $e) {
        echo "Failed to run the simple query (user-assigned).\n";
    }
    unset($conn);
} catch (PDOException $e) {
    echo "Could not connect with Authentication=ActiveDirectoryMsi (user-assigned).\n";
    print_r($e->getMessage());
    echo "\n";
}
?>
```

## <a name="example---connect-using-service-principal-objects-in-azure-active-directory"></a>Пример: подключение с помощью объектов субъекта-службы в Azure Active Directory

Для проверки подлинности с помощью объекта субъекта-службы потребуется соответствующий [идентификатор клиента приложения](/azure/active-directory/develop/howto-create-service-principal-portal#get-tenant-and-app-id-values-for-signing-in) и [секрет клиента](/azure/active-directory/develop/howto-create-service-principal-portal#option-2-create-a-new-application-secret).


### <a name="sqlsrv-driver"></a>Драйвер SQLSRV

```php
<?php

$adServer = 'myazureserver.database.windows.net';
$adDatabase = 'myazuredatabase';
$adSPClientId = 'myAppClientId';
$adSPClientSecret = 'myClientSecret';

$conn = false;
$connectionInfo = array("Database"=>$adDatabase, 
                        "Authentication"=>"ActiveDirectoryServicePrincipal",
                        "UID"=>$adSPClientId,
                        "PWD"=>$adSPClientSecret);

$conn = sqlsrv_connect($adServer, $connectionInfo);
if ($conn === false) {
    echo "Could not connect using Azure AD Service Principal." . PHP_EOL;
    print_r(sqlsrv_errors());
}

sqlsrv_close($conn);

?>
```

### <a name="pdo_sqlsrv-driver"></a>Драйвер PDO_SQLSRV

```php
<?php

$adServer = 'myazureserver.database.windows.net';
$adDatabase = 'myazuredatabase';
$adSPClientId = 'myAppClientId';
$adSPClientSecret = 'myClientSecret';

$conn = false;
try {
    $connectionInfo = "Database = $adDatabase; Authentication = ActiveDirectoryServicePrincipal;";
    $conn = new PDO("sqlsrv:server = $adServer; $connectionInfo", $adSPClientId, $adSPClientSecret);
} catch (PDOException $e) {
    echo "Could not connect using Azure AD Service Principal.\n";
    print_r($e->getMessage());
    echo PHP_EOL;
}

unset($conn);
?>
```


## <a name="see-also"></a>См. также:
[Использование Azure Active Directory с драйвером ODBC](../odbc/using-azure-active-directory.md)

[Что такое управляемые удостоверения для ресурсов Azure?](/azure/active-directory/managed-identities-azure-resources/overview)