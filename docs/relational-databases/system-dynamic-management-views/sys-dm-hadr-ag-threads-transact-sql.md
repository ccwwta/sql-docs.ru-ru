---
description: sys.dm_hadr_ag_threads (Transact-SQL)
title: sys.dm_hadr_ag_threads (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 02/08/2021
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.dm_hadr_ag_threads_TSQL
- sys.dm_hadr_ag_threads
- dm_hadr_ag_threads_TSQL
- dm_hadr_ag_threads
dev_langs:
- TSQL
helpviewer_keywords:
- Availability Groups [SQL Server], monitoring
- Availability Groups [SQL Server], WSFC clusters
- sys.dm_hadr_ag_threads catalog view
ms.assetid: ''
author: kfarlee
ms.author: kfarlee
monikerRange: ''
ms.openlocfilehash: c8487dd07e424b7edccc17b8a9587cfc91f74268
ms.sourcegitcommit: 8dc7e0ececf15f3438c05ef2c9daccaac1bbff78
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2021
ms.locfileid: "100354133"
---
# <a name="sysdm_hadr_ag_threads-transact-sql"></a>sys.dm_hadr_ag_threads (Transact-SQL)

Динамические представления телеметрии потока HADR (**sys.dm_hadr_ag_threads** и [sys.dm_hadr_db_threads](../../relational-databases/system-dynamic-management-views/sys-dm-hadr-db-threads-transact-sql.md)) позволяют пользователям быстро получить представление об использовании потоков группой доступности и базой данных высокой доступности. Понимание использования потоков является важным тестом производительности для настройки групп доступности.

Это динамическое административное представление сообщает об использовании потоков на уровне группы доступности.

|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**group_id**|**uniqueidentifier**|Идентификатор группы доступности.|
|**name**|**nvarchar(128)**|Имя группы доступности.|
|**num_databases**|**int**|Число баз данных в группе доступности.|
|**num_capture_threads**|**int**|Число потоков записи журнала, используемых всеми базами данных в этой группе доступности.|
|**num_redo_threads**|**int**|Число потоков повтора, используемых всеми базами данных в этой группе доступности.|
|**num_parallel_redo_threads**|**int**|Число параллельных потоков повтора, используемых всеми базами данных в этой группе доступности.|
|**num_hadr_threads**|**int**|Количество всех потоков Always on, используемых всеми базами данных в этой группе доступности.|

## <a name="permissions"></a>Разрешения  

 необходимо разрешение VIEW SERVER STATE на сервере.  
  
## <a name="see-also"></a>См. также:  

 [Always On динамические административные представления и функции групп доступности &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/always-on-availability-groups-dynamic-management-views-functions.md)   
 [Представления каталога групп доступности AlwaysOn (Transact-SQL)](../../relational-databases/system-catalog-views/always-on-availability-groups-catalog-views-transact-sql.md)   
 [Мониторинг групп доступности &#40;&#41;Transact-SQL ](../../database-engine/availability-groups/windows/monitor-availability-groups-transact-sql.md)   
 [Группы доступности AlwaysOn &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/always-on-availability-groups-sql-server.md)  
  