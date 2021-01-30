---
description: dbo.sysnotifications (Transact-SQL)
title: Уведомления dbo.sys(Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- dbo.sysnotifications_TSQL
- sysnotifications
- sysnotifications_TSQL
- dbo.sysnotifications
dev_langs:
- TSQL
helpviewer_keywords:
- sysnotifications system table
ms.assetid: c5150d18-e8b7-48a7-ada7-77c583af6e41
author: cawrites
ms.author: chadam
ms.openlocfilehash: 0a1cd54f7f2cafb73bba1c74674810e2a1362327
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99209632"
---
# <a name="dbosysnotifications-transact-sql"></a>dbo.sysnotifications (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Содержит одну строку для каждого уведомления.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**alert_id**|**int**|Идентификатор предупреждения.|  
|**operator_id**|**int**|Идентификатор оператора, которому должно быть отправлено это уведомление.|  
|**notification_method**|**tinyint**|Способ уведомления:<br /><br /> **1** = электронная почта<br /><br /> **2** = пейджер<br /><br /> **4**  =  **NetSend**<br /><br /> **7** = все|  
  
  
