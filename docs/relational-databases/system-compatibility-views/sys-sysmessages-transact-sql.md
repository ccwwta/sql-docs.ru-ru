---
description: sys.sysmessages (Transact-SQL)
title: Сообщения sys.sys(Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sys.sysmessages
- sysmessages
- sysmessages_TSQL
- sys.sysmessages_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysmessages system table
- sys.sysmessages compatibility view
ms.assetid: 44bee7d9-7517-4071-99be-8b36f979c7cc
author: WilliamDAssafMSFT
ms.author: wiassaf
ms.openlocfilehash: d686f63f498dcc77f15bd372a232e2583ec46c99
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99160690"
---
# <a name="syssysmessages-transact-sql"></a>sys.sysmessages (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Содержит по одной строке для каждой из системных ошибок и предупреждений, которые может вернуть компонент [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]. Компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] отображает описание ошибки на экране пользователя.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**error**|**int**|Уникальный номер ошибки.|  
|**severity**|**tinyint**|Степень серьезности ошибки.|  
|**dlevel**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**description**|**nvarchar(255)**|Объяснение ошибки с заполнителями для параметров.|  
|**msglangid**|**smallint**|Идентификатор группы системного сообщения.|  
  
## <a name="see-also"></a>См. также:  
 [Сопоставление системных таблиц с системными представлениями &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [Представления совместимости (Transact-SQL)](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
