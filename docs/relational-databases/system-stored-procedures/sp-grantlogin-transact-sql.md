---
description: sp_grantlogin (Transact-SQL)
title: sp_grantlogin (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sp_grantlogin_TSQL
- sp_grantlogin
dev_langs:
- TSQL
helpviewer_keywords:
- sp_grantlogin
ms.assetid: 0c873d99-c3bf-4eb1-948b-a46cb235ccd4
ms.author: vanto
author: VanMSFT
ms.openlocfilehash: b234748fb8e3d5f2f68973b7ff5011c401ad2616
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99208982"
---
# <a name="sp_grantlogin-transact-sql"></a>sp_grantlogin (Transact-SQL)

[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Создает имя входа на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] Вместо этого используйте [CREATE LOGIN](../../t-sql/statements/create-login-transact-sql.md) .  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
sp_grantlogin [@loginame=] 'login'  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @loginame = ] 'login'` Имя пользователя или группы Windows. Имя пользователя или группы Windows должно быть дополнено именем домена Windows в форме "пользователь *домена*" \\ , например **London\Joeb**. Аргумент *Login* имеет тип **sysname** и не имеет значения по умолчанию.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 0 (успешное завершение) или 1 (неуспешное завершение)  
  
## <a name="remarks"></a>Замечания  
 **sp_grantlogin** вызывает создание имени входа, которое поддерживает дополнительные параметры. Сведения о создании SQL Serverных имен входа см. в разделе [Create login &#40;Transact-SQL&#41;](../../t-sql/statements/create-login-transact-sql.md)  
  
 **sp_grantlogin** не может быть выполнена в пользовательской транзакции.  
  
## <a name="permissions"></a>Разрешения  
 Необходимо разрешение ALTER ANY LOGIN на сервере.  
  
## <a name="examples"></a>Примеры  
 В следующем примере используется `CREATE LOGIN` для создания [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имени входа для пользователя Windows `Corporate\BobJ.` . это предпочтительный метод.  
  
```sql
CREATE LOGIN [Corporate\BobJ] FROM WINDOWS;  
GO  
```  
  
## <a name="see-also"></a>См. также  
 [Хранимые процедуры безопасности (Transact-SQL)](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [CREATE LOGIN (Transact-SQL)](../../t-sql/statements/create-login-transact-sql.md)   
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
