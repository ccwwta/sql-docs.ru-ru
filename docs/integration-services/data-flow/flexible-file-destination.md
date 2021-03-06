---
description: Назначение "Гибкая работа с файлами"
title: Назначение "Гибкая работа с файлами" | Документы Майкрософт
ms.custom: ''
ms.date: 05/22/2019
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql13.dts.designer.afpextfiledest.f1
- sql14.dts.designer.afpextfiledest.f1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1899538413552e0381f87dd997356e885e435b58
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100339756"
---
# <a name="flexible-file-destination"></a>Назначение "Гибкая работа с файлами"

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]

Назначение **Гибкая работа с файлами** позволяет пакету служб SSIS записывать данные в различных поддерживаемых службах хранилища.

Сейчас поддерживаются службы хранилища

- [Хранилище BLOB-объектов Azure](https://azure.microsoft.com/services/storage/blobs/)
- [Azure Data Lake Storage 2-го поколения](/azure/storage/blobs/data-lake-storage-introduction)
   
Перетащите назначение **Гибкая работа с файлами** в конструктор потока данных и дважды щелкните его, чтобы открыть редактор.
  
Назначение **Гибкая работа с файлами** входит в состав [пакета дополнительных компонентов SQL Server Integration Services (SSIS) для Azure](../../integration-services/azure-feature-pack-for-integration-services-ssis.md).  

Доступны следующие свойства **редактора назначения "Гибкая работа с файлами"**.

- **Тип диспетчера соединений с файлами**. Определяет тип диспетчера подключений к источникам. Затем выберите один из указанных типов или создайте новый.
- **Путь к папке**. Указывает путь к папке назначения.
- **Имя файла.** Указывает имя файла назначения.
- **Формат файла**. Указывает формат файла назначения. Поддерживаемые форматы: **текст**, **Avro**, **ORC**, **Parquet**. Java требуется для ORC/Parquet. Подробные сведения см. [здесь](../../integration-services/azure-feature-pack-for-integration-services-ssis.md#dependency-on-java).
- **Знак-разделитель столбцов**. Указывает символ, используемый в качестве разделителя столбцов (многосимвольные разделители не поддерживаются).
- **Использовать первую строку в качестве имен столбцов**. Указывает, следует ли записывать в первую строку имена столбцов.
- **Сжать файл**. Указывает, сжимать ли файл.
- **Тип сжатия**. Указывает используемый формат сжатия. Поддерживаемые форматы: **GZIP**, **DEFLATE**, **BZIP2**.
- **Уровень сжатия**. Указывает используемый уровень сжатия.

Доступны следующие свойства **расширенного редактора**.

- **rowDelimiter:** символ, используемый для разделения строк в файле. Допускается только один знак. Значение по умолчанию — **\r\n**.
- **escapeChar:** Специальный символ, используемый для экранирования разделителя столбцов в содержимом входного файла. Не следует указывать escapeChar и quoteChar для таблицы одновременно. Допускается только один знак. Нет значения по умолчанию.
- **quoteChar:** Символ, используемый для заключения строкового значения в кавычки. Разделители столбцов и строк внутри знаков кавычек будут рассматриваться как часть строкового значения. Это свойство применяется к входному и выходному наборам данных. Не следует указывать escapeChar и quoteChar для таблицы одновременно. Допускается только один знак. Нет значения по умолчанию.
- **nullValue:** один или несколько символов, используемых для представления значения NULL. Значением **по умолчанию** является \N.
- **encodingName:** задает имя кодировки. См. раздел [Encoding.EncodingName](/dotnet/api/system.text.encoding).
- **skipLineCount:**  указывает количество непустых строк, которые нужно пропустить при чтении данных из входных файлов. Если указаны skipLineCount и firstRowAsHeader, то сначала пропускаются строки, а затем считываются данные заголовка из входного файла.
- **treatEmptyAsNull:** Указывает, следует ли интерпретировать NULL или пустую строку как значение NULL при считывании данных из входного файла. Значение **по умолчанию** — true.

После указания сведений о соединении переключитесь на страницу **Столбцы** , чтобы сопоставить столбцы источника со столбцами назначения для потока данных служб SSIS.

**Примечания о настройке разрешений для субъекта-службы**

Для работы **тестового подключения** (к хранилищу BLOB-объектов или Data Lake Storage 2-го поколения) субъекту-службе следует назначить по крайней мере роль **Читатель данных в хранилище BLOB-объектов** в учетной записи хранения.
Это осуществляется посредством [управление доступом на основе ролей (RBAC)](/azure/storage/common/storage-auth-aad-rbac-portal#assign-rbac-roles-using-the-azure-portal).

Для хранилища BLOB-объектов разрешение на запись предоставляется путем назначения по крайней мере роли **Участник данных в хранилище BLOB-объектов**.

Для Data Lake Storage 2-го поколения разрешение определяется как посредством управления доступом на основе ролей (RBAC), так и с помощью [списков управления доступом (ACL)](/azure/storage/blobs/data-lake-storage-how-to-set-permissions-storage-explorer).
Обратите внимание на то, что списки ACL настраиваются с помощью идентификатора объекта (OID) субъекта-службы для регистрации приложения, как описано [здесь](/azure/storage/blobs/data-lake-storage-access-control#how-do-i-set-acls-correctly-for-a-service-principal).
Для конфигурации RBAC, напротив, используется идентификатор приложения (клиента).
Когда субъекту безопасности предоставляются разрешения на данные RBAC посредством встроенной или пользовательской роли, эти разрешения сначала оцениваются при авторизации запроса.
Если запрошенная операция разрешена в соответствии с назначенными субъекту безопасности ролями RBAC, авторизация происходит немедленно и дополнительные проверки ACL не проводятся.
Если же субъекту безопасности роль RBAC не назначена или если запрошенная операция не соответствует предоставленному разрешению, проводятся проверки ACL, цель которых — определить, разрешено ли субъекту безопасности выполнять запрошенную операцию.
Для разрешения на запись необходимо предоставить по крайней мере разрешение на **выполнение** начиная с файловой системы приемника, а также разрешение на **запись** в папку приемника.
Можно также предоставить разрешение не ниже **участника данных в хранилище BLOB-объектов** с помощью RBAC.
Подробные сведения см. в [этой статье](/azure/storage/blobs/data-lake-storage-access-control).