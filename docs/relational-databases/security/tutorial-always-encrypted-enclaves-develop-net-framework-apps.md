---
description: Руководство по Разработка приложения .NET Framework с помощью Always Encrypted с безопасными анклавами
title: Руководство по Разработка приложения .NET Framework с помощью Always Encrypted с безопасными анклавами | Документация Майкрософт
ms.custom: ''
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
ms.openlocfilehash: 092220a2ef2715b8d5cd414ab5a4bc3e3493acb5
ms.sourcegitcommit: 8ca4b1398e090337ded64840bcb8d6c92d65c29e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2021
ms.locfileid: "98534743"
---
# <a name="tutorial-develop-a-net-framework-application-using-always-encrypted-with-secure-enclaves"></a>Руководство по Разработка приложения .NET Framework с помощью Always Encrypted с безопасными анклавами

[!INCLUDE [sqlserver2019-windows-only-asdb](../../includes/applies-to-version/sqlserver2019-windows-only-asdb.md)]

В этом руководстве содержатся сведения о разработке приложения, которое выполняет запросы к базе данных, использующие безопасный анклав на стороне сервера для [Always Encrypted с защищенными анклавами](encryption/always-encrypted-enclaves.md). 

## <a name="prerequisites"></a>Предварительные требования
Перед выполнением действий, описанных в этом руководстве, убедитесь, что вы изучили одно из следующих руководств.

- [Учебник. Начало работы с Always Encrypted и безопасными анклавами в SQL Server](tutorial-getting-started-with-always-encrypted-enclaves.md)
- [Учебник. Начало работы с Always Encrypted и безопасными анклавами в Базе данных SQL Azure](/azure/azure-sql/database/always-encrypted-enclaves-getting-started)

Кроме того, вам потребуется среда Visual Studio (рекомендуется версия 2019), которую можно скачать на странице [https://visualstudio.microsoft.com/](https://visualstudio.microsoft.com). На компьютере для разработки приложений должна быть установлена платформа .NET Framework 4.7.2 или более поздней версии.

## <a name="step-1-set-up-your-visual-studio-project"></a>Шаг 1. Настройка проекта в Visual Studio

Чтобы использовать функцию Always Encrypted с безопасными анклавами в приложении .NET Framework, вам нужно убедиться в том, что приложение создано на основе .NET Framework 4.7.2 и интегрировано с [пакетом NuGet Microsoft.SqlServer.Management.AlwaysEncrypted.EnclaveProviders](https://www.nuget.org/packages/Microsoft.SqlServer.Management.AlwaysEncrypted.EnclaveProviders). Кроме того, если вы храните главный ключ столбца в Azure Key Vault, необходимо также интегрировать приложение с [пакетом NuGet Microsoft.SqlServer.Management.AlwaysEncrypted.AzureKeyVaultProvider](https://www.nuget.org/packages/Microsoft.SqlServer.Management.AlwaysEncrypted.AzureKeyVaultProvider) версии 2.2.0 или более поздней. 

1. Запустите Visual Studio.

2. Создайте проект консольного приложения C\# (.NET Framework).

3. Убедитесь, что в проекте настроена по крайней мере платформа .NET Framework 4.7.2. Щелкните правой кнопкой мыши проект в Обозревателе решений, выберите **Свойства** и установите для параметра **Целевая платформа** значение ".NET Framework 4.7.2".

4. Установите следующий пакет NuGet. Щелкните **Инструменты** (главное меню) > **Диспетчер пакетов NuGet** > **Консоль диспетчера пакетов**. Выполните следующий код в консоли диспетчера пакетов.

   ```powershell
   Install-Package Microsoft.SqlServer.Management.AlwaysEncrypted.EnclaveProviders -IncludePrerelease
   ```

5. Если вы используете Azure Key Vault для хранения главных ключей столбцов, установите следующие пакеты NuGet, щелкнув **Инструменты** (главное меню) > **Диспетчер пакетов NuGet** > **Консоль диспетчера пакетов**. Выполните следующий код в консоли диспетчера пакетов.

   ```powershell
   Install-Package Microsoft.SqlServer.Management.AlwaysEncrypted.AzureKeyVaultProvider -IncludePrerelease -Version 2.2.0
   Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory
   ```

6. Откройте файл App.config для проекта.

7. Откройте раздел `<configuration>` и добавьте или обновите разделы `<configSections>`.

   1. Если в разделе `<configuration>` **нет** раздела `<configSections>`, добавьте приведенное ниже содержимое сразу после раздела `<configuration>`.

      ```xml
      <configSections>
        <section name="SqlColumnEncryptionEnclaveProviders" type="System.Data.SqlClient.SqlColumnEncryptionEnclaveProviderConfigurationSection, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
      </configSections>
      ```

   2. Если в разделе `<configuration>` уже содержится раздел `<configSections>`, добавьте следующую строку в раздел `<configSections>`:

      ```xml
      <section name="SqlColumnEncryptionEnclaveProviders"  type="System.   Data.SqlClient.   SqlColumnEncryptionEnclaveProviderConfigurationSection, System.   Data,  Version=4.0.0.0, Culture=neutral,    PublicKeyToken=b77a5c561934e089" />
      ```

8. В разделе `<configuration>` ниже `</configSections>` добавьте новый раздел, в котором указан поставщик анклава, который будет использоваться для подтверждения анклавов на стороне сервера и взаимодействия с ними.

   1. Если вы используете [!INCLUDE [ssnoversion-md](../../includes/ssnoversion-md.md)] и службу защиты узлов (HGS) (используете базу данных из раздела [Учебник. Начало работы с Always Encrypted и безопасными анклавами в SQL Server](tutorial-getting-started-with-always-encrypted-enclaves.md)), добавьте следующий раздел.

      ```xml
      <SqlColumnEncryptionEnclaveProviders>
        <providers>
          <add name="VBS"  type="Microsoft.SqlServer.Management.AlwaysEncrypted.EnclaveProviders.HostGuardianServiceEnclaveProvider,  Microsoft.SqlServer.Management.AlwaysEncrypted.EnclaveProviders,    Version=15.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91"/>
        </providers>
      </SqlColumnEncryptionEnclaveProviders>
      ```

      Ниже представлен полный пример файла app.config для простого консольного приложения.

      ```xml
      <?xml version="1.0" encoding="utf-8" ?>
      <configuration>
        <configSections>
          <section name="SqlColumnEncryptionEnclaveProviders" type="System.Data.SqlClient.SqlColumnEncryptionEnclaveProviderConfigurationSection, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
        </configSections>
        <SqlColumnEncryptionEnclaveProviders>
          <providers>
            <add name="VBS"  type="Microsoft.SqlServer.Management.AlwaysEncrypted.EnclaveProviders.HostGuardianServiceEnclaveProvider,  Microsoft.SqlServer.Management.AlwaysEncrypted.EnclaveProviders,    Version=15.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91"/>
          </providers>
        </SqlColumnEncryptionEnclaveProviders>
        <startup> 
         <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7.2" />
        </startup>
      </configuration>
      ```

   1. Если вы используете [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] и Аттестацию Microsoft Azure (используете базу данных из раздела [Учебник. Начало работы с Always Encrypted и безопасными анклавами в Базе данных SQL Azure](/azure/azure-sql/database/always-encrypted-enclaves-getting-started), добавьте следующий раздел.

      ```xml
      <SqlColumnEncryptionEnclaveProviders>
        <providers>
          <add name="SGX" type="Microsoft.SqlServer.Management.AlwaysEncrypted.EnclaveProviders.AzureAttestationEnclaveProvider, Microsoft.SqlServer.Management.AlwaysEncrypted.EnclaveProviders, Version=15.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91" />
        </providers>
      </SqlColumnEncryptionEnclaveProviders>
      ```

      Ниже представлен полный пример файла app.config для простого консольного приложения.

      ```xml
      <?xml version="1.0" encoding="utf-8" ?>
      <configuration>
        <configSections>
          <section name="SqlColumnEncryptionEnclaveProviders" type="System.Data.SqlClient.SqlColumnEncryptionEnclaveProviderConfigurationSection, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
        </configSections>
        <SqlColumnEncryptionEnclaveProviders>
          <providers>
            <add name="SGX" type="Microsoft.SqlServer.Management.AlwaysEncrypted.EnclaveProviders.AzureAttestationEnclaveProvider, Microsoft.SqlServer.Management.AlwaysEncrypted.EnclaveProviders, Version=15.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91" />
          </providers>
        </SqlColumnEncryptionEnclaveProviders>
        <startup> 
         <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7.2" />
        </startup>
      </configuration>
      ```

## <a name="step-2-implement-your-application-logic"></a>Шаг 2. Реализация логики приложения

Приложение подключится к базе данных **ContosoHR** из статьи [Руководство. Начало работы с Always Encrypted и безопасными анклавами в SQL Server](tutorial-getting-started-with-always-encrypted-enclaves.md) или [Учебник. Начало работы с Always Encrypted с безопасными анклавами в Базе данных SQL Azure](/azure/azure-sql/database/always-encrypted-enclaves-getting-started) и выполнит запрос, содержащий предикат `LIKE` в столбце **SSN**, а также проведет сравнение диапазонов в столбце **Salary**.

1. Замените содержимое файла Program.cs (созданного в Visual Studio) на приведенный ниже код. Обновите строку подключения к базе данных, указав имя сервера, параметры проверки подлинности и URL-адрес аттестации анклава для своей среды.

    ```cs
    using System;
    using System.Data.SqlClient;
    using System.Data;

    namespace ConsoleApp1
    {
        class Program
        {
            static void Main(string[] args)
            {
    
                string connectionString = "Data Source = myserver; Initial Catalog = ContosoHR; Column Encryption Setting = Enabled;Enclave Attestation Url = http://hgs.bastion.local/Attestation; Integrated Security = true";

                //string connectionString = "Data Source = myserver.database.windows.net; Initial Catalog = ContosoHR; Column Encryption Setting = Enabled;Enclave Attestation Url = https://myattestationprovider.uks.attest.azure.net/attest/SgxEnclave; User ID=user; Password=password";

                using (SqlConnection connection = new SqlConnection(connectionString))
                {
                    connection.Open();

                    SqlCommand cmd = connection.CreateCommand();
                    cmd.CommandText = @"SELECT [SSN], [FirstName], [LastName], [Salary] FROM [HR].[Employees] WHERE [SSN] LIKE @SSNPattern AND [Salary] > @MinSalary;";

                    SqlParameter paramSSNPattern = cmd.CreateParameter();

                    paramSSNPattern.ParameterName = @"@SSNPattern";
                    paramSSNPattern.DbType = DbType.AnsiStringFixedLength;
                    paramSSNPattern.Direction = ParameterDirection.Input;
                    paramSSNPattern.Value = "%9838";
                    paramSSNPattern.Size = 11;

                    cmd.Parameters.Add(paramSSNPattern);

                    SqlParameter MinSalary = cmd.CreateParameter();

                    MinSalary.ParameterName = @"@MinSalary";
                    MinSalary.DbType = DbType.Currency;
                    MinSalary.Direction = ParameterDirection.Input;
                    MinSalary.Value = 20000;

                    cmd.Parameters.Add(MinSalary);
                    cmd.ExecuteNonQuery();
    
                    SqlDataReader reader = cmd.ExecuteReader();
                    while (reader.Read())

                    {
                        Console.WriteLine(reader[0] + ", " + reader[1] + ", " + reader[2] + ", " + reader[3]);
                    }   
                    Console.ReadKey();
                }
            }
        }
    }
    ```

2. Выполните сборку и запустите приложение.  

## <a name="see-also"></a>См. также:

- [Using Always Encrypted with the .NET Framework Data Provider for SQL Server (Использование Always Encrypted с поставщиком данных .NET Framework для SQL Server)](encryption/develop-using-always-encrypted-with-net-framework-data-provider.md)
- [Руководство. Разработка приложения .NET с помощью Always Encrypted с безопасными анклавами](../../connect/ado-net/sql/tutorial-always-encrypted-enclaves-develop-net-apps.md)
