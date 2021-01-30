---
description: syspolicy_policy_categories (Transact-SQL)
title: syspolicy_policy_categories (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- syspolicy_policy_categories
- syspolicy_policy_categories_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- syspolicy_policy_groups view
ms.assetid: 65f080c7-771f-4cf6-a7a0-88882c637f8d
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 8cf37ae7776251f1d13c9671a65458a5a31cb285
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99180798"
---
# <a name="syspolicy_policy_categories-transact-sql"></a>syspolicy_policy_categories (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Это представление выводит по одной строке на каждую категорию политики, используемую в управлении на основе политик в данном экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Категории политик помогают организовать многочисленные политики. В следующей таблице описываются столбцы представления syspolicy_policy_groups.  
 
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|policy_category_id|**int**|Идентификатор категории политики.|  
|name|**sysname**|Имя категории политики.|  
|mandate_database_subscriptions|**bit**|Указывает, применима ли категория политики ко всем базам данных в экземпляре без явной подписки (1), или категория политики должна быть применена к базе данных с помощью явной подписки (0).|  
  
## <a name="remarks"></a>Замечания  
 Выводит список групп политик управления на основе политик.  
  
## <a name="permissions"></a>Разрешения  
 Требуется членство в роли PolicyAdministratorRole базы данных msdb.  
  
## <a name="see-also"></a>См. также  
 [Администрирование серверов с помощью управления на основе политик](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)   
 [Административные представления на основе политик (Transact-SQL)](../../relational-databases/system-catalog-views/policy-based-management-views-transact-sql.md)  
  
  
