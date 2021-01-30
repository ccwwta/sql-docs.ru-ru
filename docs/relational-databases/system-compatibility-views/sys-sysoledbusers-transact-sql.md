---
description: sys.sysoledbusers (Transact-SQL)
title: sys.sysоледбусерс (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sys.sysoledbusers
- sys.sysoledbusers_TSQL
- sysoledbusers
- sysoledbusers_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysoledbusers system table
- sys.sysoledbusers compatibility view
ms.assetid: fe924c17-9cad-4b2b-8124-1e0fd82931e3
author: WilliamDAssafMSFT
ms.author: wiassaf
ms.openlocfilehash: 4e8c134ad74b24704696b586bb362ab253dedb84
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99148536"
---
# <a name="syssysoledbusers-transact-sql"></a>sys.sysoledbusers (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

    
> [!IMPORTANT]  
>  Эта системная таблица [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] включена в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в качестве представления только для обеспечения обратной совместимости. Вместо этого рекомендуется использовать [представления каталога](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md) .  
  
 Содержит по одной строке для каждой пары пользователя и пароля для указанного связанного сервера. **таблицу sysoledbusers** хранится в базе данных **master** .  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**rmtsrvid**|**smallint**|Идентификатор защиты (SID) сервера.|  
|**rmtloginame**|**nvarchar (** 128 **)**|Имя удаленного входа, которое **логинсид** сопоставляется для связанных **рмтсервид**.|  
|**rmtpassword**|**nvarchar (** 128 **)**|Возвращает значение NULL.|  
|**логинсид**|**varbinary (** 85 **)**|Идентификатор SID локального имени входа для сопоставления.|  
|**status**|**smallint**|Если значение равно 1, то при сопоставлении необходимо использовать учетные данные пользователя.|  
|**changedate**|**datetime**|Дата последнего изменения сведений о сопоставлении.|  
  
## <a name="see-also"></a>См. также:  
 [Представления каталога (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Представления совместимости (Transact-SQL)](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
