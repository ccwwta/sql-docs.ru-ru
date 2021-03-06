---
description: Функция SQLTablePrivileges
title: Функция SQLTablePrivileges | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLTablePrivileges
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLTablePrivileges
helpviewer_keywords:
- SQLTablePrivileges function [ODBC]
ms.assetid: 8cfdb64f-64c5-47e6-ad57-0533ac630afa
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 16c813c1859e139c3d85ebf901e673f1164073e5
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99191734"
---
# <a name="sqltableprivileges-function"></a>Функция SQLTablePrivileges
**Соответствия**  
 Представленная версия: соответствие стандартам ODBC 1,0: ODBC  
  
 **Сводка**  
 **SQLTablePrivileges** возвращает список таблиц и привилегий, связанных с каждой таблицей. Драйвер возвращает сведения в виде результирующего набора для указанной инструкции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
  
SQLRETURN SQLTablePrivileges(  
     SQLHSTMT      StatementHandle,  
     SQLCHAR *     CatalogName,  
     SQLSMALLINT   NameLength1,  
     SQLCHAR *     SchemaName,  
     SQLSMALLINT   NameLength2,  
     SQLCHAR *     TableName,  
     SQLSMALLINT   NameLength3);  
```  
  
## <a name="arguments"></a>Аргументы  
 *статеменсандле*  
 Входной Маркер инструкции.  
  
 *CatalogName*  
 Входной Каталог таблиц. Если драйвер поддерживает каталоги для некоторых таблиц, но не для других, например, когда драйвер извлекает данные из разных СУБД, пустая строка ("") обозначает таблицы, не имеющие каталогов. *CatalogName* не может содержать шаблон поиска строки.  
  
 Если атрибуту инструкции SQL_ATTR_METADATA_ID присвоено значение SQL_TRUE, *CatalogName* рассматривается как идентификатор и его регистр не важен. Если это SQL_FALSE, *CatalogName* является обычным аргументом. он обрабатывается буквально, и его регистр важен. Дополнительные сведения см. [в разделе аргументы в функциях каталога](../../../odbc/reference/develop-app/arguments-in-catalog-functions.md).  
  
 *NameLength1*  
 Входной Длина в символах **CatalogName*.  
  
 *SchemaName*  
 Входной Шаблон поиска строк для имен схем. Если драйвер поддерживает схемы для некоторых таблиц, но не для других, например, когда драйвер извлекает данные из разных СУБД, пустая строка ("") обозначает те таблицы, которые не имеют схем.  
  
 Если атрибуту инструкции SQL_ATTR_METADATA_ID присвоено значение SQL_TRUE, то объект *SchemaName* рассматривается как идентификатор и его регистр не важен. Если это SQL_FALSE, то *SchemaName* является аргументом-шаблоном значения; он обрабатывается буквально, и его регистр важен.  
  
 *NameLength2*  
 Входной Длина в символах **SchemaName*.  
  
 *TableName*  
 Входной Шаблон поиска строки для имен таблиц.  
  
 Если атрибут инструкции SQL_ATTR_METADATA_ID имеет значение SQL_TRUE, *TableName* рассматривается как идентификатор и его регистр не важен. Если это SQL_FALSE, *TableName* является аргументом значения шаблона; он обрабатывается буквально, и его регистр важен.  
  
 *NameLength3*  
 Входной Длина в символах **TableName*.  
  
## <a name="returns"></a>Возвращаемое значение  
 SQL_SUCCESS, SQL_SUCCESS_WITH_INFO, SQL_STILL_EXECUTING, SQL_ERROR или SQL_INVALID_HANDLE.  
  
## <a name="diagnostics"></a>Диагностика  
 Когда **SQLTablePrivileges** возвращает SQL_ERROR или SQL_SUCCESS_WITH_INFO, связанное значение SQLSTATE может быть получено путем вызова **SQLGetDiagRec** с *параметром handletype* SQL_HANDLE_STMT и *маркером* *статеменсандле*. В следующей таблице перечислены значения SQLSTATE, обычно возвращаемые функцией **SQLTablePrivileges** , и объясняется каждый из них в контексте этой функции. Нотация "(DM)" предшествует описаниям SQLSTATE, возвращаемым диспетчером драйверов. Код возврата, связанный с каждым значением SQLSTATE, имеет SQL_ERROR, если не указано иное.  
  
|SQLSTATE|Ошибка|Описание|  
|--------------|-----------|-----------------|  
|01000|Общее предупреждение|Информационное сообщение для конкретного драйвера. (Функция возвращает SQL_SUCCESS_WITH_INFO.)|  
|08S01|Сбой канала связи|Канал связи между драйвером и источником данных, к которому был подключен драйвер, был неудачен до завершения обработки функции.|  
|24 000|Недопустимое состояние курсора|В *статеменсандле* был открыт курсор, а также был вызван **SQLFetch** или **SQLFetchScroll** . Эта ошибка возвращается диспетчером драйверов, если **SQLFetch** или **SQLFetchScroll** не вернул SQL_NO_DATA и возвращается драйвером, если **SQLFetch** или **SQLFetchScroll** вернул SQL_NO_DATA.<br /><br /> В *статеменсандле* был открыт курсор, но **SQLFetch** или **SQLFetchScroll** не был вызван.|  
|40001|Сбой сериализации|Произошел откат транзакции из-за взаимоблокировки ресурсов с другой транзакцией.|  
|40003|Неизвестное завершение инструкции|Не удалось выполнить связанное соединение во время выполнения этой функции, и состояние транзакции не может быть определено.|  
|HY000|Общая ошибка|Произошла ошибка, для которой нет определенного SQLSTATE и для которого не определен SQLSTATE для конкретной реализации. Сообщение об ошибке, возвращаемое функцией **SQLGetDiagRec** в буфере *\* MessageText* , описывает ошибку и ее причину.|  
|HY001|Ошибка выделения памяти|Драйверу не удалось выделить память, необходимую для поддержки выполнения или завершения функции.|  
|HY008|Operation canceled|Асинхронная обработка включена для *статеменсандле*. Была вызвана функция **SQLTablePrivileges** , и до ее завершения была вызвана **SQLCancel** или **склканцелхандле** в *статеменсандле*. Затем в *статеменсандле* вызывается функция **SQLTablePrivileges** .<br /><br /> Была вызвана функция **SQLTablePrivileges** , и до ее завершения была вызвана **SQLCancel** или **склканцелхандле** в *статеменсандле* из другого потока многопоточного приложения.|  
|HY009|Недопустимое использование пустого указателя|Атрибуту инструкции SQL_ATTR_METADATA_ID было присвоено значение SQL_TRUE, аргумент *CatalogName* был пустым указателем, а SQL_CATALOG_NAME *инфотипе* возвращает, что эти имена каталогов поддерживаются.<br /><br /> (DM) атрибуту инструкции SQL_ATTR_METADATA_ID было присвоено значение SQL_TRUE, а аргумент *SchemaName* или *TableName* — пустой указатель.|  
|HY010|Ошибка последовательности функций|(DM) вызвана асинхронно исполняемая функция для маркера соединения, связанного с *статеменсандле*. Эта асинхронная функция все еще выполнялась при вызове функции **SQLTablePrivileges** .<br /><br /> (DM) **SQLExecute**, **SQLExecDirect** или **SQLMoreResults** были вызваны для *статеменсандле* и возвращены SQL_PARAM_DATA_AVAILABLE. Эта функция была вызвана до получения данных для всех потоковых параметров.<br /><br /> (DM) вызывается асинхронно исполняемая функция (не эта одна) для *статеменсандле* и все еще выполнялась при вызове этой функции.<br /><br /> (DM) **SQLExecute**, **SQLExecDirect**, **SQLBulkOperations** или **SQLSetPos** были вызваны для *статеменсандле* и возвращены SQL_NEED_DATA. Эта функция была вызвана перед отправкой данных для всех параметров или столбцов данных, выполняемых во время выполнения.|  
|HY013|Ошибка управления памятью|Не удалось обработать вызов функции, так как не удалось получить доступ к базовым объектам памяти, возможно, из-за нехватки памяти.|  
|HY090|Недопустимая длина строки или буфера|(DM) значение одного из аргументов длины имени меньше 0, но не равно SQL_NTS.<br /><br /> Длина значения одного из аргументов длины имени превышает максимально допустимое значение для соответствующего квалификатора или имени.|  
|HY117|Подключение приостановлено из-за неизвестного состояния транзакции. Допускаются только функции отключения и только для чтения.|(DM) Дополнительные сведения о состоянии SUSPENDED см. в разделе [функция SQLEndTran](../../../odbc/reference/syntax/sqlendtran-function.md).|  
|HYC00|Необязательная функция не реализована|Указан каталог, а драйвер или источник данных не поддерживает каталоги.<br /><br /> Указана схема, и драйвер или источник данных не поддерживают схемы.<br /><br /> Для схемы таблицы, имени таблицы или столбца указан шаблон поиска строки, а источник данных не поддерживает шаблоны поиска для одного или нескольких из этих аргументов.<br /><br /> Сочетание текущих параметров атрибутов SQL_ATTR_CONCURRENCY и SQL_ATTR_CURSOR_TYPE не поддерживалось драйвером или источником данных.<br /><br /> Атрибуту инструкции SQL_ATTR_USE_BOOKMARKS было присвоено значение SQL_UB_VARIABLE, а атрибуту инструкции SQL_ATTR_CURSOR_TYPE задан тип курсора, для которого драйвер не поддерживает закладки.|  
|HYT00|Время ожидания истекло|Время ожидания запроса истекло до того, как источник данных вернул результирующий набор. Период ожидания задается через **SQLSetStmtAttr**, SQL_ATTR_QUERY_TIMEOUT.|  
|HYT01|Время ожидания подключения истекло|Время ожидания соединения истекло до ответа источника данных на запрос. Время ожидания соединения задается через **SQLSetConnectAttr**, SQL_ATTR_CONNECTION_TIMEOUT.|  
|IM001|Драйвер не поддерживает эту функцию|(DM) драйвер, связанный с *статеменсандле* , не поддерживает функцию.|  
|IM017|Опрос отключен в режиме асинхронного уведомления|При использовании модели уведомления опрос отключен.|  
|IM018|**Склкомплетеасинк** не был вызван для завершения предыдущей асинхронной операции с этим обработчиком.|Если предыдущий вызов функции в обработчике возвращает SQL_STILL_EXECUTING и если включен режим уведомления, то для обработки после обработки и завершения операции необходимо вызвать **склкомплетеасинк** .|  
  
## <a name="comments"></a>Комментарии  
 Аргументы *SchemaName* и *TableName* принимают шаблоны поиска. Дополнительные сведения о допустимых шаблонах поиска см. в разделе [аргументы значения шаблона](../../../odbc/reference/develop-app/pattern-value-arguments.md).  
  
 **SQLTablePrivileges** возвращает результаты в виде стандартного результирующего набора, упорядоченного по TABLE_CAT, TABLE_SCHEM, table_name, привилегии и участнику.  
  
 Чтобы определить фактическую длину столбцов TABLE_CAT, TABLE_SCHEM и TABLE_NAME, приложение может вызвать **SQLGetInfo** с параметрами SQL_MAX_CATALOG_NAME_LEN, SQL_MAX_SCHEMA_NAME_LEN и SQL_MAX_TABLE_NAME_LEN.  
  
> [!NOTE]  
>  Дополнительные сведения об общем использовании, аргументах и возвращаемых данных функций каталога ODBC см. в разделе [функции каталога](../../../odbc/reference/develop-app/catalog-functions.md).  
  
 Следующие столбцы были переименованы для ODBC *3. x*. Изменения имени столбца не влияют на обратную совместимость, так как приложения привязаны по номеру столбца.  
  
|Столбец ODBC 2,0|Столбец ODBC *3. x*|  
|---------------------|-----------------------|  
|TABLE_QUALIFIER|TABLE_CAT|  
|TABLE_OWNER|TABLE_SCHEM|  
  
 В следующей таблице перечислены столбцы результирующего набора. Дополнительные столбцы, которые выходят за пределы столбца 7 (IS_GRANTABLE), могут быть определены драйвером. Приложение должно получить доступ к столбцам, относящимся к драйверу, выполнив подсчет с конца результирующего набора, а не указав явную порядковую точку. Дополнительные сведения см. в разделе [данные, возвращаемые функциями каталога](../../../odbc/reference/develop-app/data-returned-by-catalog-functions.md).  
  
|Имя столбца|Номер столбца|Тип данных|Комментарии|  
|-----------------|-------------------|---------------|--------------|  
|TABLE_CAT (ODBC 1,0)|1|Varchar|Имя каталога; Значение NULL, если неприменимо к источнику данных. Если драйвер поддерживает каталоги для некоторых таблиц, но не для других, например, когда драйвер извлекает данные из разных СУБД, он возвращает пустую строку ("") для таблиц, не имеющих каталогов.|  
|TABLE_SCHEM (ODBC 1,0)|2|Varchar|Имя схемы; Значение NULL, если неприменимо к источнику данных. Если драйвер поддерживает схемы для некоторых таблиц, но не для других, например, когда драйвер извлекает данные из разных СУБД, он возвращает пустую строку ("") для тех таблиц, которые не имеют схем.|  
|TABLE_NAME (ODBC 1,0)|3|Varchar, не РАВНый NULL|Имя таблицы.|  
|ПРЕДОСТАВЛЯЕМЫЙ (ODBC 1,0)|4|Varchar|Имя пользователя, который предоставил право доступа; Значение NULL, если неприменимо к источнику данных.<br /><br /> Для всех строк, в которых значение в столбце GRANTEE является владельцем объекта, столбец GRANT будет "_SYSTEM".|  
|УЧАСТНИК (ODBC 1,0)|5|Varchar, не РАВНый NULL|Имя пользователя, которому была предоставлена привилегия.|  
|ПРИВИЛЕГИЯ (ODBC 1,0)|6|Varchar, не РАВНый NULL|Привилегия для таблицы. Может принимать одно из следующих действий или привилегия, относящаяся к источнику данных.<br /><br /> SELECT: участник может получать данные для одного или нескольких столбцов таблицы.<br /><br /> INSERT: участник может вставлять новые строки, содержащие данные для одного или нескольких столбцов в таблицу.<br /><br /> ОБНОВЛЕНИЕ: участник может обновлять данные в одном или нескольких столбцах таблицы.<br /><br /> DELETE: участник может удалять строки данных из таблицы.<br /><br /> ССЫЛКИ: участник может ссылаться на один или несколько столбцов таблицы в пределах ограничения (например, уникальное, ссылочное или проверочное ограничение таблицы).<br /><br /> Область действия, допускаемого получателем прав доступа к данной таблице, зависит от источника данных. Например, привилегия обновления может позволить участнику обновить все столбцы в таблице в одном источнике данных, а только те столбцы, для которых предоставлена права на обновление другого источника данных.|  
|IS_GRANTABLE (ODBC 1,0)|7|Varchar|Указывает, разрешено ли участнику предоставлять привилегии другим пользователям. «YES», «NO» или «NULL», если они неизвестны или неприменимы к источнику данных.<br /><br /> Привилегия предоставляется или предоставляется, но не может быть предоставлена одновременно. Результирующий набор, возвращаемый функцией **SQLColumnPrivileges** , никогда не будет содержать две строки, для которых все столбцы, кроме столбца IS_GRANTABLE, содержат одно и то же значение.|  
  
## <a name="code-example"></a>Пример кода  
 Пример кода подобной функции см. в разделе [SQLColumns](../../../odbc/reference/syntax/sqlcolumns-function.md).  
  
## <a name="related-functions"></a>Связанные функции  
  
|Сведения о|См.|  
|---------------------------|---------|  
|Привязка буфера к столбцу в результирующем наборе|[SQLBindCol, функция](../../../odbc/reference/syntax/sqlbindcol-function.md)|  
|Отмена обработки инструкции|[Функция SQLCancel](../../../odbc/reference/syntax/sqlcancel-function.md)|  
|Возвращение привилегий для столбца или столбцов|[Функция SQLColumnPrivileges](../../../odbc/reference/syntax/sqlcolumnprivileges-function.md)|  
|Возврат столбцов в таблице или таблицах|[SQLColumns, функция](../../../odbc/reference/syntax/sqlcolumns-function.md)|  
|Выборка одной строки или блока данных в прямом направлении|[Функция SQLFetch](../../../odbc/reference/syntax/sqlfetch-function.md)|  
|Выборка блока данных или прокрутка результирующего набора|[Функция SQLFetchScroll](../../../odbc/reference/syntax/sqlfetchscroll-function.md)|  
|Возврат статистики и индексов таблицы|[SQLStatistics, функция](../../../odbc/reference/syntax/sqlstatistics-function.md)|  
|Возврат списка таблиц в источнике данных|[Функция SQLTables](../../../odbc/reference/syntax/sqltables-function.md)|  
  
## <a name="see-also"></a>См. также:  
 [Справочник по API ODBC](../../../odbc/reference/syntax/odbc-api-reference.md)   
 [Файлы заголовков ODBC](../../../odbc/reference/install/odbc-header-files.md)
