---
description: Динамическое административное представление sys.dm_xe_session_event_actions (Transact-SQL)
title: sys.dm_xe_session_event_actions (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- dm_xe_session_event_actions_TSQL
- sys.dm_xe_session_event_actions_TSQL
- dm_xe_session_event_actions
- sys.dm_xe_session_event_actions
dev_langs:
- TSQL
helpviewer_keywords:
- extended events [SQL Server], views
- sys.dm_xe_session_event_actions dynamic management view
ms.assetid: 0c22a546-683e-4c84-ab97-1e9e95304b03
author: WilliamDAssafMSFT
ms.author: wiassaf
ms.openlocfilehash: 8c1376034630be746de9eb989f8bfb8a1e44981c
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99129251"
---
# <a name="sysdm_xe_session_event_actions-transact-sql"></a>Динамическое административное представление sys.dm_xe_session_event_actions (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Возвращает сведения о действиях сеанса событий. Действия выполняются, когда происходят события.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|event_session_address|**varbinary(8)**|Адрес сеанса событий в памяти. Не допускает значение NULL.|  
|action_name|**nvarchar(256)**|Имя действия. Не допускает значение NULL.|  
|action_package_guid|**uniqueidentifier**|Идентификатор GUID пакета, который содержит это действие. Не допускает значение NULL.|  
|event_name|**nvarchar(256)**|Имя события, для которого предназначено действие. Не допускает значение NULL.|  
|event_package_guid|**uniqueidentifier**|Идентификатор GUID пакета, который содержит это событие. Не допускает значение NULL.|  
  
## <a name="permissions"></a>Разрешения  
 необходимо разрешение VIEW SERVER STATE на сервере.  
  
### <a name="relationship-cardinalities"></a>Количество элементов связей  
  
|От|Кому|Связь|  
|----------|--------|------------------|  
|sys.dm_xe_session_event_actions.event_session_address|sys.dm_xe_sessions.address|«многие к одному»|  
|sys.dm_xe_session_event_actions sys.dm_xe_session_event_actions.action_name<br /><br /> sys.dm_xe_session_event_actions.action_package_guid|sys.dm_xe_objects.name,<br /><br /> sys.dm_xe_session_events.event_package_guid|«многие к одному»|  
|sys.dm_xe_session_event_actions sys.dm_xe_session_event_actions.event_name<br /><br /> sys.dm_xe_session_event_actions.event_package_guid|sys.dm_xe_objects.name,<br /><br /> sys.dm_xe_objects.package_guid|«многие к одному»|  
  
## <a name="see-also"></a>См. также:  
 [Динамические административные представления и функции (Transact-SQL)](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)  
  
  

