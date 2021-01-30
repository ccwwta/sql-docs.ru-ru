---
description: MSsync_states (Transact-SQL)
title: MSsync_states (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
f1_keywords:
- MSsync_states
- MSsync_states_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSsync_states system table
ms.assetid: b25e17e1-7718-432e-a442-c4946741d474
author: cawrites
ms.author: chadam
ms.openlocfilehash: 338700f614cc853b2b275d135e7ef466825e8019
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99211575"
---
# <a name="mssync_states-transact-sql"></a>MSsync_states (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  В **MSsync_states** таблице отслеживается, какая публикация все еще находится в режиме параллельного моментального снимка. Эта таблица хранится в базе данных распространителя.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**publisher_id**|**smallint**|Идентификатор издателя.|  
|**publisher_db**|**sysname**|Имя базы данных публикации.|  
|**publication_id**|**int**|Идентификатор публикации.|  
  
## <a name="see-also"></a>См. также:  
 [Сопоставление системных таблиц с системными представлениями &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [Integration Servicesные таблицы &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/integration-services-tables-transact-sql.md)   
 [Резервное копирование и восстановление таблиц &#40;Transact-SQL&#41;](../../relational-databases/system-tables/backup-and-restore-tables-transact-sql.md)   
 [Таблицы доставки журналов (Transact-SQL)](../../relational-databases/system-tables/log-shipping-tables-transact-sql.md)  
  
  
