---
description: dbo.sysjobservers (Transact-SQL)
title: dbo.sysжобсерверс (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 08/26/2019
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sysjobservers
- sysjobservers_TSQL
- dbo.sysjobservers
- dbo.sysjobservers_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysjobservers system table
ms.assetid: 9abcc20f-a421-4591-affb-62674d04575e
author: cawrites
ms.author: chadam
ms.openlocfilehash: 2aafe81cf4c28c560cf99e34e5bd721f36668a54
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99202328"
---
# <a name="dbosysjobservers-transact-sql"></a>dbo.sysjobservers (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

Хранит взаимосвязь или связь определенного задания с одним или более целевых серверов. Эта таблица хранится в базе данных msdb.
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|job_id|**uniqueidentifier**|Идентификатор задания.|  
|server_id|**int**|Идентификационный номер сервера.|  
|last_run_outcome|**tinyint**|Результат последнего выполнения задания:<br /><br /> **0** = сбой<br /><br /> **1** = выполнена<br /><br /> **2** = повторная попытка<br /><br /> **3** = Отмена<br /><br /> **4** = выполняется<br /><br /> **5** = неизвестно (см. следующий раздел "Примечания") |  
|last_outcome_ message|**nvarchar(1024)**|Сообщение (если оно существует), связанное со столбцом last_run_outcome.|  
|last_run_date|**int**|Дата последнего выполнения задания.|  
|last_run_time|**int**|Время последнего выполнения задания.|  
|last_run_duration|**int**|Продолжительность выполнения задания в часах, минутах и секундах. Вычисляемый с использованием формулы: (*ч* \* 10000) + (*минут* \* 100) + *секунды*.|  


## <a name="remarks"></a>Замечания

Значение выше *4* означает, что агент SQL не знает состояние этого задания. При создании задания для *last_run_outcome* изначально устанавливается значение *5* .


## <a name="see-also"></a>См. также:

[Агент SQL Serverные таблицы &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/sql-server-agent-tables-transact-sql.md)  
