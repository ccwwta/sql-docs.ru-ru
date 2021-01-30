---
description: sp_droplogin (Transact-SQL)
title: sp_droplogin (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sp_droplogin
- sp_droplogin_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_droplogin
ms.assetid: e58684d1-c394-48de-906e-da6ee91100c3
author: markingmyname
ms.author: maghan
ms.openlocfilehash: d24deba121b218c7dc84dd2bdb050d71d8577e3e
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99209327"
---
# <a name="sp_droplogin-transact-sql"></a>sp_droplogin (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Удаляет имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Это предотвращает доступ к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с этим именем входа.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] Вместо этого используйте [инструкцию DROP LOGIN](../../t-sql/statements/drop-login-transact-sql.md) .  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_droplogin [ @loginame = ] 'login'  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @loginame = ] 'login'` Имя входа для удаления. Аргумент *Login* имеет тип **sysname** и не имеет значения по умолчанию. *имя входа* должно уже существовать в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
## <a name="return-code-values"></a>Значения кода возврата  
 0 (успешное завершение) или 1 (неуспешное завершение)  
  
## <a name="remarks"></a>Замечания  
 **sp_droplogin** вызывает DROP LOGIN.  
  
 **sp_droplogin** не может быть выполнена в пользовательской транзакции.  
  
## <a name="permissions"></a>Разрешения  
 Необходимо разрешение ALTER ANY LOGIN на сервере.  
  
## <a name="examples"></a>Примеры  
 В следующем примере с помощью инструкции `DROP LOGIN` удаляется имя входа `Victoria` из экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Это является предпочтительным методом.  
  
```  
DROP LOGIN Victoria;  
GO  
```  
  
## <a name="see-also"></a>См. также  
 [Хранимые процедуры безопасности (Transact-SQL)](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [DROP LOGIN &#40;&#41;Transact-SQL ](../../t-sql/statements/drop-login-transact-sql.md)   
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
