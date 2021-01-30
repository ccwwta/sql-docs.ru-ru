---
description: sys.conversation_groups (Transact-SQL)
title: sys.conversation_groups (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- conversation_groups_TSQL
- conversation_groups
- sys.conversation_groups
- sys.conversation_groups_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.conversation_groups catalog view
ms.assetid: 3f35815e-2de4-42a2-a972-8f0141dad0b3
author: WilliamDAssafMSFT
ms.author: wiassaf
ms.openlocfilehash: f370a75a1797529a09f68175e4aed3864c8d6589
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99200834"
---
# <a name="sysconversation_groups-transact-sql"></a>sys.conversation_groups (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Это представление каталога содержит по одной строке для каждой группы сообщений.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**conversation_group_id**|**uniqueidentifier**|Идентификатор группы сообщений. Не допускает значения NULL.|  
|**service_id**|**int**|Идентификатор службы для диалогов в этой группе. Не допускает значения NULL.|  
|**is_system**|**bit**|Указывает на принадлежность или отсутствие принадлежности к системному экземпляру. Допускает значение NULL.|  
  
## <a name="permissions"></a>Разрешения  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Дополнительные сведения см. в разделе [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
  
