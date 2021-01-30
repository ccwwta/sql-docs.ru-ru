---
description: sys.pdw_loader_run_stages (Transact-SQL)
title: sys.pdw_loader_run_stages (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
dev_langs:
- TSQL
ms.assetid: 255681e9-323c-42c0-a63c-1f05536efdd5
author: ronortloff
ms.author: rortloff
monikerRange: '>= aps-pdw-2016'
ms.openlocfilehash: b0c0c6507a512e6eb02440735f4a7a9c41217ef8
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99206397"
---
# <a name="syspdw_loader_run_stages-transact-sql"></a>sys.pdw_loader_run_stages (Transact-SQL)
[!INCLUDE [pdw](../../includes/applies-to-version/pdw.md)]

  Содержит сведения о текущих и завершенных операциях загрузки в [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] . Эта информация сохраняется и после перезапуска системы.  
  
| Имя столбца | Тип данных | Description | Диапазон |
| ----------- | --------- | ----------- | ----- |
|run_id|**int**|Уникальный идентификатор запуска загрузчика.||  
|разместить|**nvarchar(30)**|Текущий этап выполнения.|"CREATE_STAGING", "DMS_LOAD", "LOAD_INSERT", "LOAD_CLEANUP"|  
|request_id|**nvarchar(32)**|Идентификатор запроса, выполняющего этот этап.||  
|status|**nvarchar (16)**|Состояние этого этапа.||  
|start_time|**datetime**|Время запуска этапа.||  
|end_time|**datetime**|Время завершения этапа (при наличии).|Значение NULL, если не началось или не выполняется.|  
|total_elapsed_time|**int**|Общее время (или затраченное на данный момент) выполнения этого этапа.|Если total_elapsed_time превышает максимальное значение для целого числа (24,8 дней в миллисекундах), это приведет к сбою материализации из-за переполнения.<br /><br /> Максимальное значение в миллисекундах эквивалентно 24,8 дням.|  
  
## <a name="see-also"></a>См. также:  
 [Представления каталога Azure Synapse Analytics и Parallel Data Warehouse](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md)  
  
  
