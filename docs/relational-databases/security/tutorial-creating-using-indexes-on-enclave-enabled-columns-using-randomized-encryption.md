---
title: Индексы в столбцах с поддержкой анклава с использованием случайного шифрования (руководство)
description: Из этого руководства вы узнаете, как создавать и использовать индексы в столбцах с поддержкой анклава с помощью случайного шифрования, поддерживаемого в функции Always Encrypted с безопасными анклавами для SQL Server и Базы данных SQL Azure.
ms.custom: seo-lt-2019
ms.date: 01/15/2021
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: vanto
ms.suite: sql
ms.technology: security
ms.tgt_pltfrm: ''
ms.topic: tutorial
author: jaszymas
ms.author: jaszymas
monikerRange: '>= sql-server-ver15'
ms.openlocfilehash: 5e08a42f9112379951c9fcff27693ab3700b69fd
ms.sourcegitcommit: 8ca4b1398e090337ded64840bcb8d6c92d65c29e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2021
ms.locfileid: "98534823"
---
# <a name="tutorial-create-and-use-indexes-on-enclave-enabled-columns-using-randomized-encryption"></a>Руководство по Создание и использование индексов в столбцах с поддержкой анклава с помощью случайного шифрования

[!INCLUDE [sqlserver2019-windows-only-asdb](../../includes/applies-to-version/sqlserver2019-windows-only-asdb.md)]

Из этого руководства вы узнаете, как создавать и использовать индексы в столбцах с поддержкой анклава с помощью случайного шифрования, поддерживаемого в функции [Always Encrypted с безопасными анклавами](encryption/always-encrypted-enclaves.md). Буду рассмотрены следующие темы.

> [!div class="checklist"]
> - создание индекса, если у вас есть доступ к ключам (главный ключ столбца и ключ шифрования столбца), которые обеспечивают защиту столбца.
> - создание индекса, если у вас нет доступа к ключам, которые обеспечивают защиту столбца.

## <a name="prerequisites"></a>Предварительные требования

Перед выполнением действий, описанных в этом руководстве, убедитесь, что вы изучили одно из следующих руководств.

- [Учебник. Начало работы с Always Encrypted и безопасными анклавами в SQL Server](tutorial-getting-started-with-always-encrypted-enclaves.md)
- [Учебник. Начало работы с Always Encrypted и безопасными анклавами в Базе данных SQL Azure](/azure/azure-sql/database/always-encrypted-enclaves-getting-started)

## <a name="step-1-enable-accelerated-database-recovery-adr-in-your-database"></a>Шаг 1. Ускорение восстановления базы данных (ADR)

> [!NOTE]
> Этот шаг применим только к [!INCLUDE [ssnoversion-md](../../includes/ssnoversion-md.md)]. Если вы используете [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)], пропустите этот шаг. ADR в [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] включен автоматически, и его отключение не поддерживается.

Мы настоятельно рекомендуем вам включить ADR для базы данных, прежде чем создавать первый индекс в столбце с поддержкой анклава с помощью случайного шифрования. Подробные сведения см. в разделе [Восстановление базы данных](./encryption/always-encrypted-enclaves.md#database-recovery) статьи [Always Encrypted с безопасными анклавами](./encryption/always-encrypted-enclaves.md).



1. Закройте все экземпляры SSMS, которые вы использовали при работе с предыдущим руководством. Это приведет к закрытию подключений базы данных, что обязательно для включения ADR.
1. От имени системного администратора откройте новый экземпляр SSMS и подключитесь к своему экземпляру [!INCLUDE [ssnoversion-md](../../includes/ssnoversion-md.md)] **без** включенной функции Always Encrypted для подключения к базе данных.
    1. Запустите SSMS.
    1. В диалоговом окне **Соединение с сервером** укажите имя сервера, выберите метод аутентификации и введите учетные данные.
    1. Нажмите кнопку **Параметры >>** и выберите вкладку **Always Encrypted**.
    1. Убедитесь, что флажок **Включить Always Encrypted (шифрование столбцов)** **не** установлен.
    1. Выберите **Подключиться**.
1. Откройте новое окно запроса и выполните инструкцию ниже, чтобы включить ADR.

   ```sql
   ALTER DATABASE ContosoHR SET ACCELERATED_DATABASE_RECOVERY = ON;
   ```

## <a name="step-2-create-and-test-an-index-without-role-separation"></a>Шаг 2. Создание и тестирование индекса без разделения ролей

На этом шаге вы создадите и протестируете индекс в зашифрованном столбце. Вы будете выступать в качестве отдельного пользователя, который выполняет роли администратора базы данных и владельца данных с доступом к ключам, обеспечивающим защиту данных.

1. Откройте новый экземпляр SSMS и подключитесь к экземпляру [!INCLUDE [ssnoversion-md](../../includes/ssnoversion-md.md)] **с** включенной функцией Always Encrypted для подключения к базе данных.
   1. Создайте новый экземпляр SSMS.
   1. В диалоговом окне **Соединение с сервером** укажите имя сервера, выберите метод аутентификации и введите учетные данные.
   1. Нажмите кнопку **Параметры >>** и выберите вкладку **Always Encrypted**.
   1. Установите флажок **Включить Always Encrypted (шифрование столбцов)** и укажите URL-адрес аттестации анклава (например, `http://hgs.bastion.local/Attestation` или `https://MyAttestationProvider.us.attest.azure.net/attest/SgxEnclave`).
   1. Щелкните **Подключить**.
   1. Если отобразится запрос на включение параметризации для запросов Always Encrypted, нажмите кнопку **Включить**.
1. Если отобразится запрос на включение параметризации для Always Encrypted, обязательно включите ее.
   1. Выберите пункт **Инструменты** в главном меню SSMS.
   2. Выберите **Параметры**.
   3. Выберите **Выполнение запроса** > **SQL Server** > **Дополнительно**.
   4. Убедитесь, что установлен флажок **Включить параметризацию для Always Encrypted**.
   5. Щелкните **ОК**.
1. Откройте окно запроса и выполните инструкции ниже, чтобы зашифровать столбец **LastName** в таблице **Employees**. Вы создадите и будете использовать индекс в таком столбце на следующих шагах.

   ```sql  
   ALTER TABLE [HR].[Employees]
   ALTER COLUMN [LastName] [nvarchar](50) COLLATE Latin1_General_BIN2 
   ENCRYPTED WITH (COLUMN_ENCRYPTION_KEY = [CEK1], ENCRYPTION_TYPE = Randomized, ALGORITHM = 'AEAD_AES_256_CBC_HMAC_SHA_256') NOT NULL;
   GO   
   ALTER DATABASE SCOPED CONFIGURATION CLEAR PROCEDURE_CACHE;
   GO
   ```

1. Создайте индекс в столбце **LastName**. Так как вы подключены к базе данных с включенной функцией Always Encrypted, драйвер клиента в SSMS прозрачно предоставит **CEK1** (ключ шифрования столбца, обеспечивающий защиту столбца **LastName**) анклаву, что необходимо для создания индекса.

   ```sql
   CREATE INDEX IX_LastName ON [HR].[Employees] ([LastName])
   INCLUDE ([EmployeeID], [FirstName], [SSN], [Salary]);
   GO
   ```

1. Выполните полнофункциональный запрос к столбцу **LastName** и убедитесь, что SQL Server использует индекс при выполнении запроса.
   1. В том же или в новом окне запроса убедитесь, что кнопка **Включить динамическую статистику запросов** на панели инструментов активирована.
   1. Выполните приведенный ниже запрос.

       ```sql
       DECLARE @LastNamePrefix NVARCHAR(50) = 'Aber%';
       SELECT * FROM [HR].[Employees] WHERE [LastName] LIKE @LastNamePrefix;
       GO
      ```

   1. На вкладке **Статистика динамических запросов** (в нижней части окна запроса) убедитесь, что запрос использует индекс.

## <a name="step-3-create-an-index-with-role-separation"></a>Шаг 3. Создание индекса с разделением ролей

На этом шаге вы создадите индекс в зашифрованном столбце от имени двух разных пользователей. Один пользователь — это администратор баз данных, который требуется для создания индекса, но который не имеет доступа к ключам. Другой пользователь — это владелец данных с доступом к ключам.

1. Используя экземпляр SSMS **без** включенной функции Always Encrypted, выполните инструкцию ниже, чтобы очистить индекс в столбце **LastName**.

   ```sql
   DROP INDEX IX_LastName ON [HR].[Employees]; 
   GO
   ```

1. От имени владельца данных (или приложения с доступом к ключам) поместите **CEK1** в кэш в анклаве.

   > [!NOTE]
   > Если вы не перезапустили экземпляр SQL Server после **шага 2 (создание и тестирование индекса без разделения ролей)** , этот шаг выполнять не нужно, так как **CEK1** уже присутствует в кэше. Мы добавили его, чтобы продемонстрировать, как владелец данных может передать ключ в анклав, если он еще не присутствует в нем.

   1. В экземпляре SSMS **с** включенной функцией Always Encrypted выполните в окне запроса приведенные ниже инструкции. Эта инструкция отправит все ключи шифрования столбцов с поддержкой анклава в анклав. Подробные сведения см. в статье [sp_enclave_send_keys (Transact-SQL)](../system-stored-procedures/sp-enclave-send-keys-sql.md).

        ```sql
        EXEC sp_enclave_send_keys;
        GO
        ```

   1. В качестве альтернативы для вызова указанной выше хранимой процедуры вы можете выполнить запрос DML, который применяет анклав к столбцу **LastName**. Таким образом в анклав будет введен только **CEK1**.

        ```sql
        DECLARE @LastNamePrefix NVARCHAR(50) = 'Aber%';
        SELECT * FROM [HR].[Employees] WHERE [LastName] LIKE @LastNamePrefix;
        GO
        ```

1. Создайте индекс от имени администратора баз данных.
    1. В экземпляре SSMS **без** включенной функции Always Encrypted выполните в окне запроса приведенные ниже инструкции.

        ```sql
        CREATE INDEX IX_LastName ON [HR].[Employees] ([LastName])
        INCLUDE ([EmployeeID], [FirstName], [SSN], [Salary]);
        GO
        ```

1. От имени владельца данных выполните полнофункциональный запрос к столбцу **LastName** и убедитесь, что SQL Server использует индекс при выполнении запроса.
   1. В экземпляре SSMS **с** включенной функцией Always Encrypted выберите существующее окно запроса или откройте новое и убедитесь, что кнопка **Включить динамическую статистику запросов** на панели инструментов активирована.
   1. Выполните приведенный ниже запрос. 

        ```sql
        DECLARE @LastNamePrefix NVARCHAR(50) = 'Aber%';
        SELECT * FROM [HR].[Employees] WHERE [LastName] LIKE @LastNamePrefix;
        GO
        ```

   1. На вкладке **Статистика динамических запросов** (в нижней части окна запроса) убедитесь, что запрос использует индекс.

## <a name="next-steps"></a>Дальнейшие действия
- [Руководство. Разработка приложения .NET с помощью Always Encrypted с безопасными анклавами](../../connect/ado-net/sql/tutorial-always-encrypted-enclaves-develop-net-apps.md)
- [Руководство. Разработка приложения .NET Framework с помощью Always Encrypted с безопасными анклавами](tutorial-always-encrypted-enclaves-develop-net-framework-apps.md)

## <a name="see-also"></a>См. также раздел
- [Создание и использование индексов в столбцах с помощью Always Encrypted с безопасными анклавами](encryption/always-encrypted-enclaves-create-use-indexes.md)
