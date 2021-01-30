---
description: systranschemas (Transact-SQL)
title: systranschemas (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
f1_keywords:
- systranschemas
- systranschemas_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- systranschemas system table
ms.assetid: 864c3966-cb61-4f2b-8939-ccda112de853
author: stevestein
ms.author: sstein
ms.openlocfilehash: 78242bbe5df333aa23dfd2b8c22688ef5e2e6284
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99181542"
---
# <a name="systranschemas-transact-sql"></a>systranschemas (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Таблица **systranschemas** используется для контроля изменений схемы в статьях, опубликованных в публикациях транзакций и моментальных снимков. Эта таблица хранится в базах данных публикаций и подписки.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**tabid**|**int**|Указывает статью таблицы, в которой произошло изменение схемы.|  
|**стартлсн**|**binary**|Регистрационный номер транзакции в начале изменения схемы.|  
|**ендлсн**|**binary**|Регистрационный номер транзакции в конце изменения схемы.|  
|**типа**|**int**|Тип изменения схемы.|  
  
## <a name="see-also"></a>См. также:  
 [Таблицы репликации (Transact-SQL)](../../relational-databases/system-tables/replication-tables-transact-sql.md)  
  
  
