---
title: Ограничения схемы
description: Описание ограничений схемы, которые можно использовать с методом GetSchema при использовании поставщика данных Microsoft SqlClient для SQL Server.
ms.date: 11/26/2020
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.topic: conceptual
author: David-Engel
ms.author: v-daenge
ms.reviewer: v-chmalh
ms.openlocfilehash: 8d72e2dd020f1345ceb0b68249cb3d3acd1024dc
ms.sourcegitcommit: 2add15a99df7b85d271adb261523689984dfd134
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "97051388"
---
# <a name="schema-restrictions"></a>Ограничения схемы

[!INCLUDE[appliesto-netfx-netcore-netst-md](../../includes/appliesto-netfx-netcore-netst-md.md)]

[!INCLUDE[Driver_ADONET_Download](../../includes/driver_adonet_download.md)]

Вторым необязательным параметром метода **GetSchema** являются ограничения, используемые для ограничения объема возвращаемых сведений о схеме, передаваемые методу **GetSchema** в виде массива строк. Позиция в массиве определяет значения, которые можно передать, и она эквивалентна номеру ограничения.  
  
Например, в следующей таблице описываются ограничения, поддерживаемые коллекцией схемы "Tables", использующей поставщик данных Microsoft SqlClient для SQL Server. Дополнительные ограничения для коллекций схем SQL Server перечислены в конце данного раздела.  

|Имя ограничения|имени параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Каталог|@Catalog|TABLE_CATALOG|1|  
|Владелец|@Owner|TABLE_SCHEMA|2|  
|Таблица|@Name|TABLE_NAME|3|  
|TableType|@TableType|TABLE_TYPE|4|  
 
## <a name="specifying-restriction-values"></a>Указание значений ограничения  

Чтобы использовать одно из ограничений коллекции схем Tables, необходимо создать массив строк с четырьмя элементами, затем поместить значение в элемент, совпадающий с номером ограничения. Например, чтобы ограничить таблицы, возвращаемые методом **GetSchema** только таблицами из схемы "Sales", перед передачей массива методу **GetSchema** присвойте второму элементу массива значение "Sales".  
  
> [!NOTE]
> - В коллекциях ограничений для `SqlClient` есть дополнительный столбец `ParameterName`. Столбец ограничения по умолчанию оставлен для обратной совместимости, но не учитывается. Чтобы свести к минимуму вероятности проведения атак путем внедрения кода SQL, при указании значений ограничений следует использовать параметризированные запросы, а не замену строк.  
> - Количество элементов в массиве должно быть меньше или равно количеству ограничений, поддерживаемых специальной коллекцией схем, в противном случае возникнет исключение <xref:System.ArgumentException>. Их может быть меньше максимального количества ограничений. Предполагается, что отсутствующие ограничения имеют значение NULL (без ограничений).  
  
Можно запросить поставщик данных Microsoft SqlClient для SQL Server для определения списка поддерживаемых ограничений, вызвав метод **GetSchema** с именем коллекции схем ограничений "Restrictions". Будет возвращен объект <xref:System.Data.DataTable> со списком имен коллекций и ограничений, значениями ограничений по умолчанию и номерами ограничений.  
  
### <a name="example"></a>Пример  

В приведенных ниже примерах демонстрируется использование метода <xref:Microsoft.Data.SqlClient.SqlConnection.GetSchema%2A> класса <xref:Microsoft.Data.SqlClient.SqlConnection> поставщика данных Microsoft SqlClient для SQL Server для извлечения данных схемы о всех таблицах, содержащихся в учебной базе данных **AdventureWorks**, а также для ограничения возвращаемых данных только таблицами из схемы "Sales":  

[!code-csharp[SqlClient GetSchema with restrictions#1](~/../sqlclient/doc/samples/SqlConnection_GetSchema_Restriction.cs#1)]  

## <a name="sql-server-schema-restrictions"></a>Ограничения схемы SQL Server  

 В приведенных ниже таблицах перечислены ограничения коллекций схем SQL Server.  
  
### <a name="users"></a>Пользователи  
  
|Имя ограничения|имени параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|User_Name|@Name|name|1|  
  
### <a name="databases"></a>Базы данных  
  
|Имя ограничения|имени параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Имя|@Name|Имя|1|  
  
### <a name="tables"></a>Таблицы  
  
|Имя ограничения|имени параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Каталог|@Catalog|TABLE_CATALOG|1|  
|Владелец|@Owner|TABLE_SCHEMA|2|  
|Таблица|@Name|TABLE_NAME|3|  
|TableType|@TableType|TABLE_TYPE|4|  
  
### <a name="columns"></a>Столбцы  
  
|Имя ограничения|имени параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Каталог|@Catalog|TABLE_CATALOG|1|  
|Владелец|@Owner|TABLE_SCHEMA|2|  
|Таблица|@Table|TABLE_NAME|3|  
|Столбец|@Column|COLUMN_NAME|4|  
  
### <a name="structuredtypemembers"></a>StructuredTypeMembers  
  
|Имя ограничения|имени параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Каталог|@Catalog|TABLE_CATALOG|1|  
|Владелец|@Owner|TABLE_SCHEMA|2|  
|Таблица|@Table|TABLE_NAME|3|  
|Столбец|@Column|COLUMN_NAME|4|  
  
### <a name="views"></a>Представления  
  
|Имя ограничения|имени параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Каталог|@Catalog|TABLE_CATALOG|1|  
|Владелец|@Owner|TABLE_SCHEMA|2|  
|Таблица|@Table|TABLE_NAME|3|  
  
### <a name="viewcolumns"></a>ViewColumns  
  
|Имя ограничения|имени параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Каталог|@Catalog|VIEW_CATALOG|1|  
|Владелец|@Owner|VIEW_SCHEMA|2|  
|Таблица|@Table|VIEW_NAME|3|  
|Столбец|@Column|COLUMN_NAME|4|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|Имя ограничения|имени параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Каталог|@Catalog|SPECIFIC_CATALOG|1|  
|Владелец|@Owner|SPECIFIC_SCHEMA|2|  
|Имя|@Name|SPECIFIC_NAME|3|  
|Параметр|@Parameter|PARAMETER_NAME|4|  
  
### <a name="procedures"></a>Процедуры  
  
|Имя ограничения|имени параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Каталог|@Catalog|SPECIFIC_CATALOG|1|  
|Владелец|@Owner|SPECIFIC_SCHEMA|2|  
|Имя|@Name|SPECIFIC_NAME|3|  
|Тип|@Type|ROUTINE_TYPE|4|  
  
### <a name="indexcolumns"></a>IndexColumns  
  
|Имя ограничения|имени параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Каталог|@Catalog|db_name()|1|  
|Владелец|@Owner|user_name()|2|  
|Таблица|@Table|o.name|3|  
|ConstraintName|@ConstraintName|x.name|4|  
|Столбец|@Column|c.name|5|  
  
### <a name="indexes"></a>Индексы  
  
|Имя ограничения|имени параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Каталог|@Catalog|db_name()|1|  
|Владелец|@Owner|user_name()|2|  
|Таблица|@Table|o.name|3|  
  
### <a name="userdefinedtypes"></a>UserDefinedTypes  
  
|Имя ограничения|имени параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|assembly_name|@AssemblyName|assemblies.name|1|  
|udt_name|@UDTName|types.assembly_class|2|  
  
### <a name="foreignkeys"></a>ForeignKeys  
  
|Имя ограничения|имени параметра|Значение ограничения по умолчанию|Номер ограничения|  
|----------------------|--------------------|-------------------------|------------------------|  
|Каталог|@Catalog|CONSTRAINT_CATALOG|1|  
|Владелец|@Owner|CONSTRAINT_SCHEMA|2|  
|Таблица|@Table|TABLE_NAME|3|  
|Имя|@Name|CONSTRAINT_NAME|4|  
  
## <a name="see-also"></a>См. также раздел

- [Microsoft ADO.NET для SQL Server](microsoft-ado-net-sql-server.md)
