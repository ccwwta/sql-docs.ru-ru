---
description: sys.trace_subclass_values (Transact-SQL)
title: sys.trace_subclass_values (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sys.trace_subclass_values
- trace_subclass_values_TSQL
- sys.trace_subclass_values_TSQL
- trace_subclass_values
dev_langs:
- TSQL
helpviewer_keywords:
- sys.trace_subclass_values catalog view
ms.assetid: 542b19ca-61c8-41ca-aa2e-0aba8906cc24
author: WilliamDAssafMSFT
ms.author: wiassaf
ms.openlocfilehash: f56994ed647544da390687c9e229b6657d63c815
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99208338"
---
# <a name="systrace_subclass_values-transact-sql"></a>sys.trace_subclass_values (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Представление каталога **sys.trace_subclass_values** содержит список значений именованного столбца. Эти значения производного класса не изменяются для данной версии компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].  
  
 Полный список поддерживаемых событий трассировки см. в разделе [Справочник по классам событий SQL Server](../../relational-databases/event-classes/sql-server-event-class-reference.md).  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] Вместо этого используйте представления каталога расширенных событий.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**trace_event_id**|**smallint**|Идентификатор события трассировки. Этот параметр также находится в представлении каталога **sys.trace_events** .|  
|**trace_column_id**|**smallint**|Идентификатор трассировочного столбца, используемый для перечисления. Этот параметр также находится в представлении каталога **sys.trace_columns** .|  
|**subclass_name**|**nvarchar(128)**|Интерпретация значения столбца.|  
|**subclass_value**|**smallint**|Значение столбца.|  
  
## <a name="permissions"></a>Разрешения  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Дополнительные сведения см. в разделе [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>См. также:  
 [Представления каталога объектов (Transact-SQL)](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [sys. traces &#40;&#41;Transact-SQL ](../../relational-databases/system-catalog-views/sys-traces-transact-sql.md)   
 [sys.trace_categories &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-trace-categories-transact-sql.md)   
 [sys.trace_columns &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-trace-columns-transact-sql.md)   
 [sys.trace_events &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-trace-events-transact-sql.md)   
 [sys.trace_event_bindings &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-trace-event-bindings-transact-sql.md)  
  
  
