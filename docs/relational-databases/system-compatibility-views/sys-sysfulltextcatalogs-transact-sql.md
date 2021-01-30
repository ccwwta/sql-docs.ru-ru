---
description: sys.sysfulltextcatalogs (Transact-SQL)
title: sys.sysфуллтексткаталогс (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sysfulltextcatalogs
- sys.sysfulltextcatalogs_TSQL
- sysfulltextcatalogs_TSQL
- sys.sysfulltextcatalogs
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sysfulltextcatalogs compatibility view
- sysfulltextcatalogs system table
ms.assetid: 18ac6ad5-01e8-428f-8422-a9ca29626977
author: WilliamDAssafMSFT
ms.author: wiassaf
monikerRange: '>=aps-pdw-2016||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 58f096b74cfaffc57911efb2645e4260c50bcb57
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99201399"
---
# <a name="syssysfulltextcatalogs-transact-sql"></a>sys.sysfulltextcatalogs (Transact-SQL)
[!INCLUDE [sql-asdbmi-pdw](../../includes/applies-to-version/sql-asdbmi-pdw.md)]

  Содержит сведения о полнотекстовых каталогах.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**ftcatid**|**smallint**|Идентификатор полнотекстового каталога.|  
|**name**|**sysname**|Имя полнотекстового каталога, указанное пользователем.|  
|**status**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**path**|**nvarchar(260)**|Корневой путь, указанный пользователем.<br /><br /> NULL = Путь не задан. Используется путь по умолчанию (путь для установки).|  
  
## <a name="see-also"></a>См. также:  
 [Сопоставление системных таблиц с системными представлениями &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [Представления совместимости (Transact-SQL)](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
