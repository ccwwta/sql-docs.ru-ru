---
description: sys.service_queue_usages (Transact-SQL)
title: sys.service_queue_usages (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sys.service_queue_usages
- sys.service_queue_usages_TSQL
- service_queue_usages
- service_queue_usages_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.service_queue_usages catalog view
ms.assetid: d58dcdaf-f82d-43d9-941b-f520581442bf
author: WilliamDAssafMSFT
ms.author: wiassaf
ms.openlocfilehash: 38f1bd8d054dfbc4b8a90ce9a9fa9554bee24685
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99204486"
---
# <a name="sysservice_queue_usages-transact-sql"></a>sys.service_queue_usages (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Это представление каталога возвращает по одной строке для каждой связи между службой и очередью службы. Одна служба может быть ассоциирована только с одной очередью. Очередь может быть ассоциирована с несколькими службами.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**service_id**|**int**|Идентификатор службы. Уникально в пределах базы данных. Не допускает значения NULL.|  
|**service_queue_id**|**int**|Идентификатор используемой очереди службы. Не допускает значения NULL.|  
  
## <a name="permissions"></a>Разрешения  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Дополнительные сведения см. в разделе [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>См. также:  
 [sys. Services &#40;&#41;Transact-SQL ](../../relational-databases/system-catalog-views/sys-services-transact-sql.md)  
  
  
