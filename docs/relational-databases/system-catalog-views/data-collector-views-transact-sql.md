---
description: Представления сборщика данных (Transact-SQL)
title: Представления сборщика данных (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- data collector view
- data collector [SQL Server], views
ms.assetid: a005e885-7813-4c7e-b332-b01d9e9d4054
author: WilliamDAssafMSFT
ms.author: wiassaf
ms.openlocfilehash: bf304e44eb5f4374d4fdc1de21d7dc73fee2d72e
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99184307"
---
# <a name="data-collector-views-transact-sql"></a>Представления сборщика данных (Transact-SQL)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

  Тип сборщика данных предоставляет следующие представления для вывода сведений о конфигурации сборщика данных, например свойств сборщика данных, наборов сбора и элементов наборов сбора, а также для вывода статистики выполнения при работе сборщика данных. Эти представления, которые находятся в базе данных **msdb** , также предоставляют уровень абстракции для базовых таблиц. Уровень абстракции повышает безопасность, предотвращая прямой доступ к таблицам и одновременно разрешая изменять таблицы, не затрагивая связанных с ними приложений.  

:::row:::
    :::column:::
        [syscollector_collection_items (Transact-SQL)](../../relational-databases/system-catalog-views/syscollector-collection-items-transact-sql.md)
        
        [syscollector_collector_types (Transact-SQL)](../../relational-databases/system-catalog-views/syscollector-collector-types-transact-sql.md)
        
        [syscollector_execution_log (Transact-SQL)](../../relational-databases/system-catalog-views/syscollector-execution-log-transact-sql.md)
        
        [syscollector_execution_stats (Transact-SQL)](../../relational-databases/system-catalog-views/syscollector-execution-stats-transact-sql.md)
    :::column-end:::
    :::column:::
        [syscollector_collection_sets (Transact-SQL)](../../relational-databases/system-catalog-views/syscollector-collection-sets-transact-sql.md)
        
        [syscollector_config_store (Transact-SQL)](../../relational-databases/system-catalog-views/syscollector-config-store-transact-sql.md)
        
        [syscollector_execution_log_full (Transact-SQL)](../../relational-databases/system-catalog-views/syscollector-execution-log-full-transact-sql.md)
    :::column-end:::
:::row-end:::
  
## <a name="see-also"></a>См. также:  
 [Сбор данных](../../relational-databases/data-collection/data-collection.md)   
 [Хранимые процедуры сборщика данных (Transact-SQL)](../../relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql.md)  
  
  
