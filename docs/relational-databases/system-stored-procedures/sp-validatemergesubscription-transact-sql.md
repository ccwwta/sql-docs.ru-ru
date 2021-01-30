---
description: sp_validatemergesubscription (Transact-SQL)
title: sp_validatemergesubscription (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
f1_keywords:
- sp_validatemergesubscription
- sp_validatemergesubscription_TSQL
helpviewer_keywords:
- sp_validatemergesubscription
ms.assetid: d73ad03c-e5b3-4606-a0ee-7d75e12762a6
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 15ebc99d11b0ff009d80f769ea9fbfad60f11c76
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99201816"
---
# <a name="sp_validatemergesubscription-transact-sql"></a>sp_validatemergesubscription (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Выполняет проверку правильности для указанной подписки. Эта хранимая процедура выполняется на издателе в базе данных публикации.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_validatemergesubscription [@publication=] 'publication'  
        , [ @subscriber = ] 'subscriber'  
        , [ @subscriber_db = ] 'subscriber_db'  
        , [ @level = ] level  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @publication = ] 'publication'` Имя публикации. Аргумент *publication* имеет тип **sysname** и не имеет значения по умолчанию.  
  
`[ @subscriber = ] 'subscriber'` Имя подписчика. Аргумент *Subscriber* имеет тип **sysname** и не имеет значения по умолчанию.  
  
`[ @subscriber_db = ] 'subscriber_db'` Имя базы данных подписки. Аргумент *subscriber_db* имеет тип **sysname** и не имеет значения по умолчанию.  
  
`[ @level = ] 'level'` Тип выполняемой проверки. *Level* имеет тип **tinyint** и не имеет значения по умолчанию. Уровень может быть одним из значений.  
  
|Значение уровня|Описание|  
|-----------------|-----------------|  
|**1**|Проверка достоверности только количества строк.|  
|**2**|Проверка по количеству строк и контрольной сумме.|  
|**3**|Проверка достоверности по количеству строк и двоичной контрольной сумме.|  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (сбой)  
  
## <a name="remarks"></a>Замечания  
 **sp_validatemergesubscription** используется в репликации слиянием.  
  
## <a name="permissions"></a>Разрешения  
 Только члены предопределенной роли сервера **sysadmin** или предопределенной роли базы данных **db_owner** могут выполнять **sp_validatemergesubscription**.  
  
## <a name="see-also"></a>См. также:  
 [Хранимые процедуры репликации (Transact-SQL)](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)   
 [Проверка реплицированных данных](../../relational-databases/replication/validate-data-at-the-subscriber.md)   
 [sp_validatemergepublication &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-validatemergepublication-transact-sql.md)  
  
  
