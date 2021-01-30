---
description: sp_delete_targetsvrgrp_member (Transact-SQL)
title: sp_delete_targetsvrgrp_member (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sp_delete_targetsvrgrp_member_TSQL
- sp_delete_targetsvrgrp_member
dev_langs:
- TSQL
helpviewer_keywords:
- sp_delete_targetsvrgrp_member
ms.assetid: 178a38d9-9b19-4648-95d7-e1397110d14c
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 4b363c9be51bb46339bfd6caac4ae389dda0a8b2
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99199131"
---
# <a name="sp_delete_targetsvrgrp_member-transact-sql"></a>sp_delete_targetsvrgrp_member (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Удаляет целевой сервер из группы целевых серверов.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_delete_targetsvrgrp_member [ @group_name = ] 'group_name' , [ server_name = ] 'server_name'   
```  
  
## <a name="arguments"></a>Аргументы  
`[ @group_name = ] 'group_name'` Имя группы. Аргумент *group_name* имеет тип **sysname** и не имеет значения по умолчанию.  
  
`[ @server_name = ] 'server_name'` Имя сервера, удаляемого из указанной группы. *server_name* имеет тип **nvarchar (30)** и не имеет значения по умолчанию.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (сбой)  
  
## <a name="result-sets"></a>Результирующие наборы  
 None  
  
## <a name="permissions"></a>Разрешения  
 Для выполнения этой хранимой процедуры пользователям должна быть предоставлена предопределенная роль сервера **sysadmin** .  
  
## <a name="examples"></a>Примеры  
 В следующем примере сервер `LONDON1` удаляется из группы «Servers Maintaining Customer Information».  
  
```  
USE msdb ;  
GO  
  
EXEC sp_delete_targetsvrgrp_member   
    @group_name = N'Servers Maintaining Customer Information',  
    @server_name = N'LONDON1';  
GO  
```  
  
## <a name="see-also"></a>См. также:  
 [sp_add_targetsvrgrp_member &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-add-targetsvrgrp-member-transact-sql.md)   
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
