---
description: Представление совместимости sys.sysfiles (Transact-SQL)
title: sys.sysфайловых групп (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sysfilegroups_TSQL
- sys.sysfilegroups
- sysfilegroups
- sys.sysfilegroups_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysfilegroups system table
- sys.sysfilegroups compatibility view
ms.assetid: e567fa07-31cd-43cc-b8c7-ba6108baca80
author: WilliamDAssafMSFT
ms.author: wiassaf
ms.openlocfilehash: 9d0a11ac6a62ee7f2936e3c31f8e99389b2bd10c
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99160719"
---
# <a name="syssysfilegroups-transact-sql"></a>Представление совместимости sys.sysfiles (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Содержит по одной строке для каждой файловой группы в базе данных. Таблица содержит по крайней мере одну запись для первичной файловой группы.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**Идентификатор**|**smallint**|Уникальный для каждой базы данных идентификатор группы.|  
|**allocpolicy**|**smallint**|Зарезервировано|  
|**status**|**int**|0x8 = только для чтения<br /><br /> 0x10 = по умолчанию|  
|**Группа**|**sysname**|Имя файловой группы.|  
  
## <a name="see-also"></a>См. также:  
 [Сопоставление системных таблиц с системными представлениями &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [Представления совместимости (Transact-SQL)](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
