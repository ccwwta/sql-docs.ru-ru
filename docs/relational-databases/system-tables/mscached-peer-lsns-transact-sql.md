---
description: MScached_peer_lsns (Transact-SQL)
title: MScached_peer_lsns (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
f1_keywords:
- MScached_peer_lsns_TSQL
- MScached_peer_lsns
dev_langs:
- TSQL
helpviewer_keywords:
- MScached_peer_lsns system table
ms.assetid: f8b6089a-0230-45f9-8c34-9fe0d2a3a74e
author: cawrites
ms.author: chadam
ms.openlocfilehash: 974f15aa4e1c971f6f3ca6abe6d9a31129611dfd
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99160490"
---
# <a name="mscached_peer_lsns-transact-sql"></a>MScached_peer_lsns (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Таблица **MScached_peer_lsns** используется для трассировки значений LSN в журнале транзакций, которые используются для определения команд, возвращаемых данному подписчику в одноранговой репликации. Эта таблица хранится в базе данных распространителя.  
  
## <a name="definition"></a>Определение  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**agent_id**|**int**|Идентификатор агента распространителя.|  
|**правителю**|**sysname**|Имя исходного издателя.|  
|**originator_db**|**sysname**|Имя базы данных исходной публикации.|  
|**originator_publication_id**|**int**|Идентифицирует исходную публикацию.|  
|**originator_db_version**|**int**|Показывает номер версии исходной базы данных.|  
|**originator_lsn**|**varbinary (16)**|LSN-номер транзакции.|  
  
## <a name="remarks"></a>Замечания  
 Значения LSN используются немедленно после вставки и не имеют последующего значения для системы.  
  
## <a name="see-also"></a>См. также:  
 [Таблицы репликации &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Представления репликации (Transact-SQL)](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
