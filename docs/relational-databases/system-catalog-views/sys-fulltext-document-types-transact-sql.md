---
description: sys.fulltext_document_types (Transact-SQL)
title: sys.fulltext_document_types (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sys.fulltext_document_types_TSQL
- fulltext_document_types
- fulltext_document_types_TSQL
- sys.fulltext_document_types
dev_langs:
- TSQL
helpviewer_keywords:
- sys.fulltext_document_types catalog view
ms.assetid: 156fcfa4-7304-4a5c-b96f-1c3e061e5df0
author: pmasl
ms.author: pelopes
ms.reviewer: mikeray
monikerRange: =azuresqldb-current||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 209e7585bfae7009c55447416c150b6a352a1111
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99193895"
---
# <a name="sysfulltext_document_types-transact-sql"></a>sys.fulltext_document_types (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Возвращает строку для каждого типа документа, который является доступным для операций полнотекстового индексирования. Каждая строка представляет интерфейс IFilter, который зарегистрирован в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**document_type**|**sysname**|Расширение файла поддерживаемого типа документа.<br /><br /> Это значение можно использовать для определения фильтра, который будет использоваться во время полнотекстового индексирования столбцов типа **varbinary (max)** или **Image**.|  
|**class_id**|**uniqueidentifier**|Идентификатор GUID класса IFilter, который поддерживает расширение файла.|  
|**path**|**nvarchar(260)**|Путь к IFilter DLL. Путь является видимым только для элементов предопределенной роли сервера **serveradmin** .|  
|**version**|**sysname**|Версия IFilter DLL.|  
|**производителя**|**sysname**|Название производителя IFilter.<br /><br /> Примечание. поддерживаются только документы с изготовителем [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssSDS](../../includes/sssds-md.md)] .|  
  
## <a name="permissions"></a>Разрешения  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)]  
  
## <a name="see-also"></a>См. также:  
 [Представления каталога (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
