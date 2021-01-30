---
description: MSagent_parameters (Transact-SQL)
title: MSagent_parameters (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
f1_keywords:
- MSagent_parameters_TSQL
- MSagent_parameters
dev_langs:
- TSQL
helpviewer_keywords:
- MSagent_parameters system table
ms.assetid: be30abc9-c00d-446f-b1b4-1269772f37e6
author: cawrites
ms.author: chadam
ms.openlocfilehash: 5f11e54327bc3ed5ae59f4dc3ef22ee56f51ed18
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99160524"
---
# <a name="msagent_parameters-transact-sql"></a>MSagent_parameters (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  **MSagent_parameters** таблица содержит параметры, связанные с профилем агента. Параметры имеют те же имена, что и поддерживаемые агентом. Эта таблица хранится в базе данных **msdb** .  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**profile_id**|**int**|Идентификатор профиля из таблицы **MSagent_profiles** .|  
|**parameter_name**|**sysname**|Имя параметра.|  
|**value**|**nvarchar(255)**|Значение параметра.|  
  
## <a name="see-also"></a>См. также:  
 [Таблицы репликации &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Представления репликации (Transact-SQL)](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
