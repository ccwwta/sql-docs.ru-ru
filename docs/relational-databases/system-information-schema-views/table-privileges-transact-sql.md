---
description: TABLE_PRIVILEGES (Transact-SQL)
title: TABLE_PRIVILEGES (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- TABLE_PRIVILEGES_TSQL
- TABLE_PRIVILEGES
dev_langs:
- TSQL
helpviewer_keywords:
- INFORMATION_SCHEMA.TABLE_PRIVILEGES view
- TABLE_PRIVILEGES view
ms.assetid: 70269d26-b085-4a98-8a9f-b4742c2848bd
author: VanMSFT
ms.author: vanto
monikerRange: =azuresqldb-current||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: d5517f01dc9af5b392104a6d6c17a828296e0385
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99185458"
---
# <a name="table_privileges-transact-sql"></a>TABLE_PRIVILEGES (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Возвращает по одной строке для каждого права доступа к таблице, предоставляемого текущему пользователю или текущим пользователем в текущей базе данных.  
  
 Чтобы получить сведения из этих представлений, укажите полное имя **INFORMATION_SCHEMA.** _view_name_.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**GRANTOR**|**nvarchar (** 128 **)**|Лицо, предоставляющее права доступа.|  
|**GRANTEE**|**nvarchar (** 128 **)**|Лицо, получающее права доступа.|  
|**TABLE_CATALOG**|**nvarchar (** 128 **)**|Квалификатор таблицы.|  
|**TABLE_SCHEMA**|**nvarchar (** 128 **)**|Имя схемы, содержащей таблицу.<br /><br /> Важно только надежный способ найти схему объекта — запросить представление каталога sys. objects. <strong> \* \* \* \* </strong>|  
|**TABLE_NAME**|**sysname**|Имя таблицы.|  
|**PRIVILEGE_TYPE**|**varchar (** 10 **)**|Тип прав доступа.|  
|**IS_GRANTABLE**|**varchar (** 3 **)**|Определяет, может ли участник, предоставлять разрешения другим пользователям.|  
  
## <a name="see-also"></a>См. также:  
 [Системные представления &#40;&#41;Transact-SQL ](../../t-sql/language-reference.md)   
 [Представления информационной схемы &#40;&#41;Transact-SQL ](~/relational-databases/system-information-schema-views/system-information-schema-views-transact-sql.md)   
 [sys.objects (Transact-SQL)](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md)   
 [sys.database_permissions (Transact-SQL)](../../relational-databases/system-catalog-views/sys-database-permissions-transact-sql.md)   
 [sys.server_permissions (Transact-SQL)](../../relational-databases/system-catalog-views/sys-server-permissions-transact-sql.md)  
  
