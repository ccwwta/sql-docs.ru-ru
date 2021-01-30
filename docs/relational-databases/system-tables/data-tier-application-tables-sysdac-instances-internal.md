---
description: Таблицы приложений уровня данных — sysdac_instances_internal
title: sysdac_instances_internal (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sysdac_instances_internal_TSQL
- sysdac_instances_internal
dev_langs:
- TSQL
helpviewer_keywords:
- sysdac_instances_internal
ms.assetid: d2d52cc4-3463-431a-b779-6fbfdeee1dfc
author: cawrites
ms.author: chadam
ms.openlocfilehash: 043c3a116799d8ab76b02b982c2a5ce3ec19fa83
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99187928"
---
# <a name="data-tier-application-tables---sysdac_instances_internal"></a>Таблицы приложений уровня данных — sysdac_instances_internal
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Отображает по одной строке для каждого экземпляра приложения уровня данных (DAC), развернутого на экземпляре [!INCLUDE[ssDE](../../includes/ssde-md.md)]. Эта таблица хранится в схеме dbo в базе данных msdb.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|instance_id|**uniqueidentifier**|Идентификатор экземпляра DAC.|  
|имя_экземпляра|**sysname**|Имя экземпляра DAC, указанное при развертывании экземпляра.|  
|type_name|**sysname**|Имя DAC, указанное при создании пакета DAC.|  
|type_version|**nvarchar (64)**|Версия DAC, указанная при создании пакета DAC.|  
|description|**nvarchar(4000)**|Описание DAC, записанное при создании пакета DAC.|  
|type_stream|**varbinary(max)**|Битовый поток, содержащий закодированное представление логических объектов (например, таблиц и представлений), которые содержатся в DAC.|  
|date_created|**datetime**|Дата и время создания экземпляра DAC.|  
|created_by|**sysname**|Имя входа, создавшее экземпляр DAC.|  
  
## <a name="remarks"></a>Замечания  
 Доступ только для чтения к этому представлению доступен всем пользователям с разрешениями на подключение к базе данных master.  
  
## <a name="permissions"></a>Разрешения  
 Требует членства в предопределенной роли сервера sysadmin.  
  
## <a name="see-also"></a>См. также:  
 [Приложения уровня данных](../../relational-databases/data-tier-applications/data-tier-applications.md)   
 [dbo.sysdac_instances &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/data-tier-application-views-dbo-sysdac-instances.md)  
  
  
