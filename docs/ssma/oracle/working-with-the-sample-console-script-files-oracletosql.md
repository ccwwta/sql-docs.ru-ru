---
description: Работа с образцами файлов сценария консоли (OracleToSQL)
title: Работа с примерами файлов сценариев консоли (OracleToSQL) | Документация Майкрософт
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Sample Console Script Files, ServersConnectionFileSample.xml
- Sample Console Script Files, SqlStatementConversionSample.xml
- Sample Console Script Files,VariableValueFileSample.xml
ms.assetid: c6202dcc-b994-457b-9b2f-0cd89e79792d
author: nahk-ivanov
ms.author: alexiva
manager: alexiva
ms.openlocfilehash: e8f26a02082dad9533044617771c1525fffd467e
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100080705"
---
# <a name="working-with-the-sample-console-script-files-oracletosql"></a>Работа с образцами файлов сценария консоли (OracleToSQL)
Несколько примеров файлов предоставлены вместе с продуктом для ссылки и использования пользователя. В этом разделе описывается, как с легкостью настроить эти сценарии в соответствии с потребностями конечного пользователя.  
  
## <a name="sample-console-script-files"></a>Примеры файлов сценариев консоли  
Для справки пользователя предоставлены следующие примеры файлов сценариев консоли, охватывающих различные сценарии:  
  
-   ServersConnectionFileSample.xml  
  
-   VariableValueFileSample.xml  
  
-   AssessmentReportGenerationSample.xml  
  
-   SqlStatementConversionSample.xml  
  
-   ConversionAndDataMigrationSample.xml  
  
-   **ServersConnectionFileSample.xml:**  
  
    -   Этот пример предоставляет различные режимы подключения к исходной и целевой базе данных, и пользователь может выбрать любой режим в соответствии с требованием. Этот пример содержит определения сервера.  
  
    -   Пользователь может подключиться к требуемой базе данных, просто изменив значения на необходимые определения исходного и целевого серверов. В приведенном примере все значения были предоставлены в виде значений переменных, доступных в **VariableValueFileSample.xml**.  Все остальные параметры соединения можно удалить из файла подключения рабочего сервера пользователя.  
  
    -   Дополнительные сведения о подключении к исходному и целевому серверу см. в разделе [Создание файлов подключения к серверу &#40;OracleToSQL&#41;](../../ssma/oracle/creating-the-server-connection-files-oracletosql.md) .  
  
-   **VariableValueFileSample.xml:** Все переменные, которые использовались в примерах файлов сценариев консоли и были `ServersConnectionFileSample.xml` упорядочены по копиям в этом файле. Для выполнения примеров сценариев консоли пользователь должен просто заменить примеры значений переменных определяемыми пользователем и передать этот файл в качестве дополнительного аргумента командной строки вместе с файлом скрипта.  
  
    Дополнительные сведения о файле значений переменных см. в разделе [Создание файлов переменных значений &#40;OracleToSQL&#41;](../../ssma/oracle/creating-variable-value-files-oracletosql.md).  
  
-   **AssessmentReportGenerationSample.xml:** Этот пример позволяет пользователю создать отчет по оценке XML, который пользователь может использовать для анализа, прежде чем он начнет преобразовывать и переносить данные.  
  
    В `generate-assessment-report` команде пользователь должен мандаторили изменить значение переменной (см. **VariableValueFileSample.xml**) в атрибуте, указав `object-name` имя базы данных, используемое пользователем. В зависимости от типа указанного объекта `object-type` значение также потребуется изменить.  
  
    Если пользователь должен оценить несколько объектов или баз данных, он может указать несколько `metabase-object` узлов, как показано в `generate-assessment-report` примере 4 примера файла сценария консоли.  
  
    Дополнительные сведения о создании отчетов см. в разделе [Создание отчетов &#40;OracleToSQL&#41;](../../ssma/oracle/generating-reports-oracletosql.md).  
  
    > [!NOTE]  
    > -   Убедитесь, что аргумент командной строки файла переменной value передается в консольное приложение, а VariableValueFileSample.xml обновляется указанными пользователем значениями.  
    > -   Убедитесь, что в консольное приложение передается аргумент командной строки файла подключения к серверу, а ServersConnectionFileSample.xml обновляется с использованием правильных значений параметров сервера.  
  
-   **SqlStatementConversionSample.xml:**  
    Этот пример позволяет пользователю создавать соответствующий `t-sql` скрипт для команды базы данных Source, `sql` предоставленной в качестве входного.  
  
    В `convert-sql-statement` команде пользователь должен мандаторили изменить значение переменной (см. **VariableValueFileSample.xml**) в атрибуте, указав `context` имя базы данных, используемое пользователем. Пользователю также потребуется изменить `sql` значение атрибута на команду базы данных `sql` -источника, которую требуется преобразовать.  
  
    Пользователь может также предоставлять файлы SQL для преобразования. Это показано в `convert-sql-statement` примере 4 команды файла сценария консоли.  
  
    > [!NOTE]  
    > Убедитесь, что аргумент командной строки файла переменной value передается в консольное приложение, а VariableValueFileSample.xml обновляется указанными пользователем значениями.  
  
-   **ConversionAndDataMigrationSample.xml:**  
     Этот пример позволяет пользователю выполнить сквозную миграцию из преобразования в миграцию данных. Список обязательных значений атрибутов, которые необходимо изменить, приведен ниже.  
  
    **Имя команды**  
  
    `map-schema`  
  
    Сопоставление схемы базы данных источника с целевой схемой.  
  
    **Attribute**  
  
    -   `source-schema:` Указывает базу данных источника, которую необходимо преобразовать.  
  
    -   `sql-server-schema`: Указывает целевую базу данных, в которую будет выполнена миграция  
  
    **Имя команды**  
  
    `convert-schema`  
  
    -   Выполняет преобразование схемы из источника в целевую схему.  
  
    -   Если пользователь должен оценить несколько объектов или баз данных, он может указать несколько `metabase-object` узлов, как показано в `convert-schema` примере 4 примера файла сценария консоли.  
  
    **Attribute**  
  
    `object-name`: Укажите имя базы данных-источника или объект, который необходимо преобразовать. Убедитесь, что соответствующие `object-type` изменения основаны на типе объекта, который указан в `object-name`  
  
    **Имя команды**  
  
    `synchronize-target`  
  
    -   Синхронизирует целевые объекты с целевой базой данных.  
  
    -   Если пользователь должен оценить несколько объектов или баз данных, он может указать несколько `metabase-object` узлов, как показано в `synchronize-target` примере 3 примера файла сценария консоли.  
  
    **Attribute**  
  
    `object-name:` Укажите имя базы данных или объекта SQL Server, который необходимо создать. Убедитесь, что соответствующие `object-type` изменения основаны на типе объекта, который указан в `object-name`  
  
    **Имя команды**  
  
    `migrate-data`  
  
    -   Переносит исходные данные в целевой объект.  
  
    -   Если пользователь должен оценить несколько объектов или баз данных, он может указать несколько `metabase-object` узлов, как показано в `migrate-data` примере 2 примера файла сценария консоли.  
  
    **Attribute**  
  
    `object-name:` Указывает имя базы данных-источника или таблицы, которые необходимо перенести. Убедитесь, что соответствующие `object-type` изменения основаны на типе объекта, который указан в `object-name`  
  
## <a name="see-also"></a>См. также:  
[Создание файлов переменных значений &#40;OracleToSQL&#41;](../../ssma/oracle/creating-variable-value-files-oracletosql.md)  
[Создание файлов подключения к серверу &#40;OracleToSQL&#41;](../../ssma/oracle/creating-the-server-connection-files-oracletosql.md)  
[Создание отчетов &#40;OracleToSQL&#41;](../../ssma/oracle/generating-reports-oracletosql.md)  
  
