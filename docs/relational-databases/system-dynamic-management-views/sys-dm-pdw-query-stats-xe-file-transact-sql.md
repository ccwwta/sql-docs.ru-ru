---
description: sys.dm_pdw_query_stats_xe_file (Transact-SQL)
title: sys.dm_pdw_query_stats_xe_file (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
dev_langs:
- TSQL
ms.assetid: e0cd402f-04d0-4a5b-b725-88b31bb7862e
author: WilliamDAssafMSFT
ms.author: wiassaf
monikerRange: '>= aps-pdw-2016'
ms.openlocfilehash: b2791d178cc725070cbce0662052ebe69a6ec542
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99139425"
---
# <a name="sysdm_pdw_query_stats_xe_file-transact-sql"></a>sys.dm_pdw_query_stats_xe_file (Transact-SQL)
[!INCLUDE [pdw](../../includes/applies-to-version/pdw.md)]

  Это динамическое административное представление является устаревшим и будет удалено в следующем выпуске. В этом выпуске он возвращает 0 строк.  
  
|Имя столбца|Тип данных|Description|Диапазон|  
|-----------------|---------------|-----------------|-----------|  
|event|**nvarchar(60)**|Ключ для этого представления.||  
|.|**xml**|||  
|pdw_node_id|**int**|Узел, на котором работает экземпляр XEvent.||  
  
## <a name="see-also"></a>См. также:  
 [Динамические административные представления Azure синапсе Analytics и Параллельное хранилище данных &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
