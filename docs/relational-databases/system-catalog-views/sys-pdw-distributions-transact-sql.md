---
description: sys.pdw_distributions (Transact-SQL)
title: sys.pdw_distributions (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: reference
dev_langs:
- TSQL
ms.assetid: 572b5187-9753-4063-adf8-65dea87d11f8
author: ronortloff
ms.author: rortloff
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest'
ms.openlocfilehash: bc73b551c49ae7d568adec7ff84fbbe3c529ea45
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99199300"
---
# <a name="syspdw_distributions-transact-sql"></a>sys.pdw_distributions (Transact-SQL)
[!INCLUDE[applies-to-version/asa-pdw](../../includes/applies-to-version/asa-pdw.md)]

  Содержит сведения о распределениях на устройстве. В нем отображается одна строка для каждого распределения устройства.  
  
|Имя столбца|Тип данных|Description|Диапазон|  
|-----------------|---------------|-----------------|-----------|  
|distribution_id|**int**|Уникальный числовой идентификатор, связанный с распределением.<br /><br /> Ключ для этого представления.|1 на число единиц вычислений на устройстве, умноженное на число распределений на каждый узел вычислений.|  
|pdw_node_id|**int**|Идентификатор узла, на котором находится это распространение.|См. pdw_node_id в [sys.dm_pdw_nodes &#40;&#41;Transact-SQL ](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-nodes-transact-sql.md).|  
|name|**nvarchar(32)**|Идентификатор строки, связанный с распределением, используемый в качестве суффикса в распределенных таблицах.|Строка, состоящая из "A-Z", "a-z", "0-9", "_", "-".|  
|position|**int**|Расположение распределения в узле, соответствующем другим распределениям на этом узле.|1 — число распределений на узел.|  
  
## <a name="see-also"></a>См. также:  
 [Представления каталога Azure Synapse Analytics и Parallel Data Warehouse](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md)  
  
  
