---
description: sysdbmaintplan_databases (Transact-SQL)
title: sysdbmaintplan_databases (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sysdbmaintplan_databases
- sysdbmaintplan_databases_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysdbmaintplan_databases system table
ms.assetid: f8413a44-8fcc-4899-84f2-b4afe0f8ec08
author: cawrites
ms.author: chadam
ms.openlocfilehash: 459d4bae13d7a2526acc124bf4d26220919cf750
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99178021"
---
# <a name="sysdbmaintplan_databases-transact-sql"></a>sysdbmaintplan_databases (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Эта таблица включена для сохранения существующих сведений об экземплярах, обновленных с предыдущей версии [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздние версии не изменяют содержимое этой таблицы. Эта таблица хранится в базе данных **msdb** .  
  
 [!INCLUDE[ssNoteDepNextAvoid](../../includes/ssnotedepnextavoid-md.md)]  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**plan_id**|**Uniqueidentifier**|Идентификатор плана обслуживания.|  
|**database_name**|**sysname**|Имя базы данных, связанной с планом обслуживания базы данных.|  
  
  
