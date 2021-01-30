---
description: dbo.syscategories (Transact-SQL)
title: Категории dbo.sys(Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- dbo.syscategories_TSQL
- syscategories
- syscategories_TSQL
- dbo.syscategories
dev_langs:
- TSQL
helpviewer_keywords:
- syscategories system table
ms.assetid: eb2cb75c-dc58-4a5b-b329-664e9fe20ce0
author: cawrites
ms.author: chadam
ms.openlocfilehash: c1d7bf545605d8ebbf34f45e1b8d3b9a45e89c2f
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99211286"
---
# <a name="dbosyscategories-transact-sql"></a>dbo.syscategories (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Содержит категории, используемые средой [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] для организации заданий, предупреждений и операторов. Эта таблица хранится в базе данных **msdb** .  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**category_id**|**int**|Идентификатор категории|  
|**category_class**|**int**|Тип элемента в категории:<br /><br /> **1** = задание<br /><br /> **2** = оповещение<br /><br /> **3** = оператор|  
|**category_type**|**tinyint**|Тип категории:<br /><br /> **1** = локальный<br /><br /> **2** = многосерверная<br /><br /> **3** = нет|  
|**name**|**sysname**|Имя категории|  
  
  
