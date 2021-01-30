---
description: DOMAIN_CONSTRAINTS (Transact-SQL)
title: DOMAIN_CONSTRAINTS (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- DOMAIN_CONSTRAINTS
- DOMAIN_CONSTRAINTS_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- INFORMATION_SCHEMA.DOMAIN_CONSTRAINTS view
- DOMAIN_CONSTRAINTS view
ms.assetid: 436c4480-f1e3-403f-b2bd-de04539afe3c
author: markingmyname
ms.author: maghan
monikerRange: =azuresqldb-current||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 0382fd441570730c2e5781fc90027855d0730ff7
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99189288"
---
# <a name="domain_constraints-transact-sql"></a>DOMAIN_CONSTRAINTS (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Возвращает по одной строке для каждого из псевдонимов типов данных в текущей базе данных, к которым привязано правило и которые доступны текущему пользователю.  
  
 Чтобы получить сведения из этих представлений, укажите полное имя **INFORMATION_SCHEMA.** _view_name_.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**CONSTRAINT_CATALOG**|**nvarchar (** 128 **)**|База данных, в которой находится правило.|  
|**CONSTRAINT_SCHEMA**|**nvarchar (** 128 **)**|Имя схемы, содержащей ограничение.<br /><br /> Важно. не используйте INFORMATION_SCHEMA представления для определения схемы объекта. <strong> \* \* \* \* </strong> INFORMATION_SCHEMA представления представляют только подмножество метаданных объекта. Единственный надежный способ найти схему объекта — направить запрос к представлению каталога sys.objects.|  
|**CONSTRAINT_NAME**|**sysname**|Имя правила.|  
|**DOMAIN_CATALOG**|**nvarchar (** 128 **)**|База данных, в которой существует псевдоним типа данных.|  
|**DOMAIN_SCHEMA**|**nvarchar (** 128 **)**|Имя схемы, содержащей псевдоним типа данных.<br /><br /> Важно. не используйте INFORMATION_SCHEMA представления для определения схемы типа данных. <strong> \* \* \* \* </strong> Единственный надежный способ найти схему типа — использовать функцию TYPEPROPERTY.|  
|**DOMAIN_NAME**|**sysname**|Псевдоним типа данных.|  
|**IS_DEFERRABLE**|**varchar (** 2 **)**|Указывает, возможна ли отсрочка проверки ограничения. Всегда возвращает NO.|  
|**INITIALLY_DEFERRED**|**varchar (** 2 **)**|Указывает, отложена ли первоначальная проверка ограничения. Всегда возвращает NO.|  
  
## <a name="see-also"></a>См. также:  
 [Системные представления &#40;&#41;Transact-SQL ](../../t-sql/language-reference.md)   
 [Представления информационной схемы &#40;&#41;Transact-SQL ](~/relational-databases/system-information-schema-views/system-information-schema-views-transact-sql.md)   
 [sys.objects (Transact-SQL)](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md)   
 [sys.types (Transact-SQL)](../../relational-databases/system-catalog-views/sys-types-transact-sql.md)  
  
