---
description: VIEW_COLUMN_USAGE (Transact-SQL)
title: VIEW_COLUMN_USAGE (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- VIEW_COLUMN_USAGE
- VIEW_COLUMN_USAGE_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- INFORMATION_SCHEMA.VIEW_COLUMN_USAGE view
- VIEW_COLUMN_USAGE view
ms.assetid: fc0b3608-a7e8-4532-8215-32235d6670f1
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 3f72b7a0555615a3bb4852ef61e5bdb62f98eeca
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99190081"
---
# <a name="view_column_usage-transact-sql"></a>VIEW_COLUMN_USAGE (Transact-SQL)
[!INCLUDE [sql-asdb-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  Возвращает по одной строке для каждого столбца в текущей базе данных, используемой в определении представления. Это представление информационной схемы возвращает сведения об объектах, на которые у текущего пользователя есть разрешения.  
  
 Чтобы получить сведения из этих представлений, укажите полное имя **INFORMATION_SCHEMA.** _view_name_.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**VIEW_CATALOG**|**nvarchar (** 128 **)**|Квалификатор представления.|  
|**VIEW_SCHEMA**|**nvarchar (** 128 **)**|Имя схемы, содержащей представление.<br /><br /> **&#42;&#42; важно &#42;&#42;**  только надежный способ найти схему объекта — запросить представление каталога sys. objects.|  
|**VIEW_NAME**|**sysname**|Имя представления.|  
|**TABLE_CATALOG**|**nvarchar (** 128 **)**|Квалификатор таблицы.|  
|**TABLE_SCHEMA**|**nvarchar (** 128 **)**|Имя схемы, содержащей таблицу.<br /><br /> **&#42;&#42; важно &#42;&#42;**  только надежный способ найти схему объекта — запросить представление каталога sys. objects.|  
|**TABLE_NAME**|**sysname**|Базовая таблица.|  
|**COLUMN_NAME**|**sysname**|Имя столбца.|  
  
## <a name="see-also"></a>См. также:  
 [Системные представления &#40;&#41;Transact-SQL ](../../t-sql/language-reference.md)   
 [Представления информационной схемы &#40;&#41;Transact-SQL ](~/relational-databases/system-information-schema-views/system-information-schema-views-transact-sql.md)   
 [sys.sql_dependencies &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-sql-dependencies-transact-sql.md)   
 [sys.objects (Transact-SQL)](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md)  
  
