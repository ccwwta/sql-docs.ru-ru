---
description: sys.check_constraints (Transact-SQL)
title: sys.check_constraints (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/28/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sys.check_constraints
- sys.check_constraints_TSQL
- check_constraints_TSQL
- check_constraints
dev_langs:
- TSQL
helpviewer_keywords:
- sys.check_constraints catalog view
ms.assetid: 940ebc5e-44ba-4dae-8b29-da94f2d1d6c4
author: VanMSFT
ms.author: vanto
monikerRange: =azuresqldb-current||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: f1248a45505b06ca40255c77f093aa36ee0b2909
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99188841"
---
# <a name="syscheck_constraints-transact-sql"></a>sys.check_constraints (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Содержит по одной строке для каждого объекта, который является проверочным ограничением, с **sys. objects. Type** = ' C '.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**\<Columns inherited from sys.objects>**||Список столбцов, наследуемых этим представлением, см. в разделе [sys. objects &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md).|  
|**is_disabled**|**bit**|Ограничение CHECK отключено.|  
|**is_not_for_replication**|**bit**|Ограничение CHECK было создано с параметром NOT FOR REPLICATION.|  
|**is_not_trusted**|**bit**|Ограничение CHECK не было подтверждено системой для всех строк.|  
|**parent_column_id**|**int**|Значение 0 указывает на ограничение CHECK на уровне таблицы.<br /><br /> Ненулевое значение указывает на ограничение CHECK уровня столбца, определенное в столбце с указанным значением идентификатора.|  
|**definition**|**nvarchar(max)**|Выражение SQL, которым определяется это ограничение CHECK.|  
|**uses_database_collation**|**bit**|1 = определение ограничения зависит от принятых по умолчанию параметров сортировки базы данных для правильной оценки; в противном случае — 0. Такая зависимость предотвращает изменение параметров сортировки по умолчанию для базы данных.|  
|**is_system_named**|**bit**|1 = имя сформировано системой.<br /><br /> 0 = имя предоставлено пользователем.|  
  
## <a name="permissions"></a>Разрешения  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Дополнительные сведения см. в разделе [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>См. также:  
 [Представления каталога объектов (Transact-SQL)](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [Представления каталога (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
