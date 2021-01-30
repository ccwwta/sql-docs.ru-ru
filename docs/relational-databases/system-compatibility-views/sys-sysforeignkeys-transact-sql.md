---
description: sys.sysforeignkeys (Transact-SQL)
title: sys.sysфореигнкэйс (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sysforeignkeys
- sys.sysforeignkeys
- sys.sysforeignkeys_TSQL
- sysforeignkeys_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysforeignkeys system table
- sys.sysforeignkeys compatibility view
ms.assetid: 41544236-1c46-4501-be88-18c06963b6e8
author: WilliamDAssafMSFT
ms.author: wiassaf
ms.openlocfilehash: edbb686df3d410b6049bca2799e0f10b2ff07db8
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99158525"
---
# <a name="syssysforeignkeys-transact-sql"></a>sys.sysforeignkeys (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Содержит данные об ограничениях FOREIGN KEY, включенных в определения таблиц базы данных.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**constid**|**int**|Идентификатор ограничения FOREIGN KEY.|  
|**fkeyid**|**int**|Идентификатор объекта таблицы с ограничением FOREIGN KEY.|  
|**rkeyid**|**int**|Идентификатор объекта таблицы, на которую ссылается ограничение FOREIGN KEY.|  
|**fkey**|**smallint**|Идентификатор ссылающегося столбца.|  
|**rkey**|**smallint**|Идентификатор столбца, на который указывает ссылка.|  
|**keyno**|**smallint**|Положение столбца в списке ссылочных столбцов.|  
  
## <a name="see-also"></a>См. также:  
 [Сопоставление системных таблиц с системными представлениями &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [Представления совместимости (Transact-SQL)](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
