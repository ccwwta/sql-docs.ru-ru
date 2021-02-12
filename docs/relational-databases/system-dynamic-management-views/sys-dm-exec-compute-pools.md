---
description: sys.dm_exec_compute_pools (Transact-SQL)
title: sys.dm_exec_compute_pools (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2019
ms.prod: sql
ms.prod_service: database-engine, big-data-clusters
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sys.dm_exec_compute_pools
- dm_exec_compute_pools_TSQL
- dm_exec_compute_pools
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_exec_compute_pools dynamic management view
ms.assetid: ''
author: WilliamDAssafMSFT
ms.author: wiassaf
monikerRange: '>=sql-server-ver15||>=sql-server-linux-2017'
ms.openlocfilehash: 7e9459c31529b8446b49b776ed009c429f904b18
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100071588"
---
# <a name="sysdm_exec_compute_pools-transact-sql"></a>sys.dm_exec_compute_pools (Transact-SQL)
[!INCLUDE[sqlserver2019](../../includes/applies-to-version/sqlserver2019.md)]

|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|name|`sysname`|Имя пула вычислений. Не допускает значение NULL. Возвращает `default` для пула вычислений по умолчанию. |
|compute_pool_id|`int`|Уникальный идентификатор пула. Ключ для этого представления.|  
|location|`sysname`|Конечная точка для контроллера в кластере больших данных SQL. Не допускает значение NULL. |

## <a name="permissions"></a>Разрешения

В [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] необходимо `VIEW SERVER STATE` разрешение.

## <a name="see-also"></a>См. также:

[Что [!INCLUDE[big-data-clusters-2019](../../includes/ssbigdataclusters-ss-nover.md)] ](../../big-data-cluster/big-data-cluster-overview.md)?
