---
description: sys.server_event_session_targets (Transact-SQL)
title: sys.server_event_session_targets (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- server_event_session_targets_TSQL
- sys.server_event_session_targets_TSQL
- sys.server_event_session_targets
- server_event_session_targets
dev_langs:
- TSQL
helpviewer_keywords:
- sys.server_event_session_targets catalog view
- xe
ms.assetid: dda4879d-57ae-4267-b410-1ef5c37404c7
author: WilliamDAssafMSFT
ms.author: wiassaf
ms.openlocfilehash: d69b9273cbcf67484568300793ece0cb8f0c05e9
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99172639"
---
# <a name="sysserver_event_session_targets-transact-sql"></a>sys.server_event_session_targets (Transact-SQL)
[!INCLUDE[sqlserver](../../includes/applies-to-version/sqlserver.md)]

  Возвращает строку для каждой цели события для сеанса событий.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|event_session_id|**int**|Идентификатор сеанса событий. Не допускает значение NULL.|  
|target_id|**int**|Идентификатор цели. Идентификатор уникален внутри объекта сеанса событий. Не допускает значение NULL.|  
|name|**sysname**|Имя цели события. Не допускает значение NULL.|  
|Пакет|**sysname**|Имя пакета событий, который содержит цель события. Не допускает значение NULL.|  
|module|**sysname**|Имя модуля, который содержит цель события. Не допускает значение NULL.|  
  
## <a name="permissions"></a>Разрешения  
 необходимо разрешение VIEW SERVER STATE на сервере.  
  
## <a name="remarks"></a>Замечания  
 Это представление имеет следующее количество элементов связей.  
  
| От | Кому | Связь |
| ---- | -- | ------------ |
|sys.server_event_session_targets.event_session_id|sys.server_event_sessions sys.server_event_sessions.event_session_id|Многие к одному|  
  
## <a name="see-also"></a>См. также:  
 [Представления каталога (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Представления каталога расширенных событий &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/extended-events-catalog-views-transact-sql.md)   
 [Расширенные события](../../relational-databases/extended-events/extended-events.md)  
  
  
