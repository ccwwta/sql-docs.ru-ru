---
title: sys.sp_rda_get_rpo_duration (Transact-SQL) | Документация Майкрософт
description: Используйте sys.sp_rda_get_rpo_duration, чтобы получить количество часов переносимых данных, которые SQL Server хранить в промежуточной таблице для полного восстановления удаленной базы данных Azure.
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
f1_keywords:
- sys.sp_rda_get_rpo_duration
- sys.sp_rda_get_rpo_duration_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sp_rda_get_rpo_duration stored procedure
ms.assetid: 35882067-3072-47ff-9024-ca453c0f49a7
author: markingmyname
ms.author: maghan
ms.openlocfilehash: c5c84b580f2a51ad9507db2fbece327a3ca71608
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99211796"
---
# <a name="syssp_rda_get_rpo_duration-transact-sql"></a>sys.sp_rda_get_rpo_duration (Transact-SQL)
[!INCLUDE [sqlserver2016](../../includes/applies-to-version/sqlserver2016.md)]

  Возвращает количество часов перенесенных данных, которые SQL Server сохранены в промежуточной таблице, чтобы обеспечить полное восстановление удаленной базы данных Azure, если требуется восстановление на момент времени. 
  
  Дополнительные сведения см. [в разделе Stretch Database уменьшается риск потери данных в Azure за счет временного сохранение перенесенных строк](../../sql-server/stretch-database/backup-stretch-enabled-databases-stretch-database.md#stretchRPO).  
    
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)    
    
## <a name="syntax"></a>Синтаксис    
    
```    
    
sp_rda_get_rpo_duration @durationinhours output    
    
```    
    
## <a name="output-parameter"></a>Выходной параметр    
 *\@дуратионинхаурс*    
  Число часов (целое значение, отличное от NULL) переносимых данных, которые SQL Server сохранены для текущей базы данных с поддержкой растяжения.    
    
## <a name="permissions"></a>Разрешения    
 Требуются db_owner разрешения.    
    
## <a name="remarks"></a>Замечания    
 Измените значение, выполнив [sys.sp_rda_set_rpo_duration &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-rda-set-rpo-duration-transact-sql.md).    
    
## <a name="see-also"></a>См. также:    
 [sys.sp_rda_set_rpo_duration &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-rda-set-rpo-duration-transact-sql.md)     
 [Восстановление баз данных с поддержкой Stretch (Stretch Database)](../../sql-server/stretch-database/restore-stretch-enabled-databases-stretch-database.md)    
 [База данных Stretch](../../sql-server/stretch-database/stretch-database.md)    
    
  
