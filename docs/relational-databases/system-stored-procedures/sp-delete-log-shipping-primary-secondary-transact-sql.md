---
description: sp_delete_log_shipping_primary_secondary (Transact-SQL)
title: sp_delete_log_shipping_primary_secondary (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sp_delete_log_shipping_primary_secondary_TSQL
- sp_delete_log_shipping_primary_secondary
dev_langs:
- TSQL
helpviewer_keywords:
- sp_delete_log_shipping_primary_secondary
ms.assetid: d6f71a12-f7b1-4a1c-9639-a533b8287b0c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: aad84b3a0d02300c0b26a457bc4e16fc21a41dbc
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99211130"
---
# <a name="sp_delete_log_shipping_primary_secondary-transact-sql"></a>sp_delete_log_shipping_primary_secondary (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Удаляет запись базы данных-получателя на сервере-источнике.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_delete_log_shipping_primary_secondary  
    [ @primary_database = ] 'primary_database',   
    [ @secondary_server = ] 'secondary_server',   
    [ @secondary_database = ] 'secondary_database'  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @primary_database = ] 'primary_database'` Имя базы данных на сервере-источнике. Аргумент *primary_database* имеет тип **sysname** и не имеет значения по умолчанию.  
  
`[ @secondary_server = ] 'secondary_server'` Имя сервера-получателя. Аргумент *secondary_server* имеет тип **sysname** и не имеет значения по умолчанию.  
  
`[ @secondary_database = ] 'secondary_database'` Имя базы данных-получателя. Аргумент *secondary_database* имеет тип **sysname** и не имеет значения по умолчанию.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 0 (успешное завершение) или 1 (неуспешное завершение)  
  
## <a name="result-sets"></a>Результирующие наборы  
 Нет.  
  
## <a name="remarks"></a>Remarks  
 **sp_delete_log_shipping_primary_secondary** должны быть запущены из базы данных **master** на сервере источника. Эта хранимая процедура удаляет запись для базы данных-получателя из **log_shipping_primary_secondaries** на сервере-источнике.  
  
## <a name="permissions"></a>Разрешения  
 Необходимо членство в предопределенной роли сервера **sysadmin** .  
  
## <a name="examples"></a>Примеры  
 В следующем примере хранимая процедура `sp_delete_log_shipping_primary_secondary` используется для удаления базы данных-получателя `LogShipAdventureWorks` с сервера-получателя `FLATIRON`.  
  
```  
EXEC master.dbo.sp_delete_log_shipping_primary_secondary  
@primary_database = N'AdventureWorks'  
,@secondary_server = N'FLATIRON'  
,@secondary_database = N'LogShipAdventureWorks';  
GO  
```  
  
## <a name="see-also"></a>См. также:  
 [Сведения о доставке журналов (SQL Server)](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
