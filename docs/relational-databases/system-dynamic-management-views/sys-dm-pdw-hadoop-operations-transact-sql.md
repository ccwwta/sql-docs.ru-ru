---
description: sys.dm_pdw_hadoop_operations (Transact-SQL)
title: sys.dm_pdw_hadoop_operations (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: reference
dev_langs:
- TSQL
ms.assetid: 5d2337d4-e2c7-48de-9c26-cdc7e6eb5d55
author: ronortloff
ms.author: rortloff
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest'
ms.openlocfilehash: 92b2ca358d1c1ef012af00159d94f30b0ce035a3
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99142414"
---
# <a name="sysdm_pdw_hadoop_operations-transact-sql"></a>sys.dm_pdw_hadoop_operations (Transact-SQL)
[!INCLUDE[applies-to-version/asa-pdw](../../includes/applies-to-version/asa-pdw.md)]

  Содержит по одной строке для каждого задания Map-reduce, которое передается в Hadoop в ходе выполнения [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] запроса к внешней таблице Hadoop. Каждое задание Map-reduce представляет один из предикатов в запросе. Используется, только если предикат включение включен для запросов к внешним таблицам Hadoop.  
  
|Имя столбца|Тип данных|Description|Диапазон|  
|-----------------|---------------|-----------------|-----------|  
|request_id|**nvarchar(32)**|Идентификатор для этой внешней операции Hadoop.|То же, что и идентификатор в [sys.dm_pdw_exec_requests &#40;&#41;Transact-SQL ](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-requests-transact-sql.md).|  
|step_index|**int**|Индекс шага запроса, который ссылается на эту операцию Hadoop.|То же, что и step_index в [sys.dm_pdw_request_steps &#40;&#41;Transact-SQL ](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-request-steps-transact-sql.md).|  
|operation_type|**nvarchar(255)**|Описывает тип внешней операции.|"Внешняя операция Hadoop"|  
|operation_name|**nvarchar(4000)**|Идентификатор задания для задания Map-reduce. Это значение возвращается службой Hadoop после [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] отправки задания.||  
|map_progress|**float**|Процент входных данных, которые были использованы заданием Map до сих пор.|Число с плавающей запятой между, включая, 0 и 100.|  
|reduce_progress|**int**|Процент завершенного задания сокращения.|Число с плавающей запятой между, включая, 0 и 100.|  
  
## <a name="see-also"></a>См. также:  
 [Системные представления &#40;&#41;Transact-SQL ](../../t-sql/language-reference.md)  
  
