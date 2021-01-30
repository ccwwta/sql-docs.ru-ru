---
description: sys.event_notification_event_types (Transact-SQL)
title: sys.event_notification_event_types (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sys.event_notification_event_types_TSQL
- sys.event_notification_event_types
- event_notification_event_types_TSQL
- event_notification_event_types
dev_langs:
- TSQL
helpviewer_keywords:
- sys.event_notification_event_types catalog view
ms.assetid: 73dae456-7044-4b00-b0bd-990ef810b356
author: WilliamDAssafMSFT
ms.author: wiassaf
monikerRange: =azuresqldb-current||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 23f843b7996f527ac55a2bc05416c7a3ca8d9ca0
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99203880"
---
# <a name="sysevent_notification_event_types-transact-sql"></a>sys.event_notification_event_types (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Возвращает строку для каждого события или группы событий, для которых может запускаться уведомление о событии.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**type**|**int**|Тип события или группы событий, которые являются причиной срабатывания уведомления о событии.|  
|**type_name**|**nvarchar(128)**|Имя события или группы событий. Его можно указать в предложении FOR инструкции [CREATE EVENT NOTIFICATION](../../t-sql/statements/create-event-notification-transact-sql.md) .|  
|**parent_type**|**int**|Тип группы событий, являющейся родителем для события или группы событий.|  
  
## <a name="permissions"></a>Разрешения  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Дополнительные сведения см. в разделе [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>См. также:  
 [Представления каталога объектов (Transact-SQL)](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [Представления каталога (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
