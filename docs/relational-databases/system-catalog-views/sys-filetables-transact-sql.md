---
description: sys.filetables (Transact-SQL)
title: sys. FileTable (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- filetables
- filetables_TSQL
- sys.filetables
- sys.filetables_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.filetables catalog view
ms.assetid: a740be59-cd52-4707-9ad2-5203669a63ac
author: WilliamDAssafMSFT
ms.author: wiassaf
ms.openlocfilehash: 144091f2574f428433c515bee2df13054f7eb5c6
ms.sourcegitcommit: 38e055eda82d293bf5fe9db14549666cf0d0f3c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2021
ms.locfileid: "99250110"
---
# <a name="sysfiletables-transact-sql"></a>sys.filetables (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Возвращает по одной строке для каждой таблицы FileTable в [!INCLUDE[ssnoversion](../../includes/ssnoversion-md.md)]. Дополнительные сведения о таблицах FileTable см. в разделе [Таблицы FileTable (SQL Server)](../../relational-databases/blob/filetables-sql-server.md).    
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**object_id**||Идентификационный номер объекта. Уникален в базе данных.<br /><br /> Дополнительные сведения см [. в таблице sys. objects &#40;&#41;Transact-SQL ](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md).|  
|**is_enabled**|**bit**|1 = Таблица FileTable находится во включенном состоянии.|  
|**directory_name**|**varchar (255)**|Имя корневого каталога для таблицы FileTable.|  
|**filename_collation_id**||Является идентификатором параметров сортировки, определенных для таблицы FileTable|  
|**filename_collation_name**||Является именем параметров сортировки, определенных для таблицы FileTable|  
  
## <a name="see-also"></a>См. также:  
 [Управление таблицами FileTable](../../relational-databases/blob/manage-filetables.md)   
 [FileTables (SQL Server)](../../relational-databases/blob/filetables-sql-server.md)  
  
  
