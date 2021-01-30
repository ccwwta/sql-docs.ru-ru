---
description: MSdistribution_status (Transact-SQL)
title: MSdistribution_status (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
f1_keywords:
- MSdistribution_status_TSQL
- MSdistribution_status
dev_langs:
- TSQL
helpviewer_keywords:
- MSdistribution_status view
ms.assetid: 90d447de-3a4a-4f3e-aeab-e8fff6348361
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0f1b28e357588e039e78ccf862d7f04aac6e024a
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99160371"
---
# <a name="msdistribution_status-transact-sql"></a>MSdistribution_status (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Представление **MSdistribution_status** предоставляет дополнительные сведения о командах состояния в базе данных распространителя. Это представление хранится в базе данных распространителя.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**article_id**|**int**|Определяет статью.|  
|**agent_id**|**int**|Определяет агента репликации.|  
|**UndelivCmdsInDistDB**|**int**|Количество команд, ожидающих доставки на подписчики.|  
|**DelivCmdsInDistDB**|**int**|Количество команд, доставленных на подписчики.|  
  
## <a name="see-also"></a>См. также:  
 [Таблицы репликации &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Представления репликации (Transact-SQL)](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
