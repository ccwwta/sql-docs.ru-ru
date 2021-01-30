---
description: MSmerge_errorlineage (Transact-SQL)
title: MSmerge_errorlineage (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
f1_keywords:
- MSmerge_errorlineage_TSQL
- MSmerge_errorlineage
dev_langs:
- TSQL
helpviewer_keywords:
- MSmerge_errorlineage system table
ms.assetid: 3bcbd328-c958-4cd4-a573-3c35539fa919
author: cawrites
ms.author: chadam
ms.openlocfilehash: 9dcf7f8db0a5d02a64657e00046667b07d1e29e3
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99171680"
---
# <a name="msmerge_errorlineage-transact-sql"></a>MSmerge_errorlineage (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Таблица **MSmerge_errorlineage** содержит строки, которые были удалены на подписчике, но удаление не распространяется на издатель. Эта таблица хранится в базах данных публикации и подписки.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**tablenick**|**int**|Целочисленное значение, присваиваемое таблице, публикуемой для выполнения репликации слиянием. Соответствует полю псевдонима в таблице **sysmergearticles** .|  
|**уникаль**|**uniqueidentifier**|Идентификатор строки.|  
|**журнала преобразований**|**varbinary (501)**|Хранит список обновлений строки подписчиками и издателями. Используется для выявления и разрешения конфликтных ситуаций.|  
  
## <a name="see-also"></a>См. также:  
 [Таблицы репликации &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Представления репликации (Transact-SQL)](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
