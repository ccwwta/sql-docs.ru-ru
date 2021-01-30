---
description: sp_replflush (Transact-SQL)
title: sp_replflush (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
f1_keywords:
- sp_replflush
- sp_replflush_TSQL
helpviewer_keywords:
- sp_replflush
ms.assetid: 20809f5f-941d-427f-8f0c-de7a6c487584
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 45a015f0b7b2448c0cf19c147247e1dd09b565b2
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99211899"
---
# <a name="sp_replflush-transact-sql"></a>sp_replflush (Transact-SQL)
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

  Очищает кэш статьи. Эта хранимая процедура выполняется на издателе в базе данных публикации.  
  
> [!IMPORTANT]  
>  Выполнять эту процедуру вручную нет необходимости. **sp_replflush** следует использовать только для устранения неполадок репликации, направленных опытным специалистом службы поддержки репликации.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_replflush  
```  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (сбой)  
  
## <a name="remarks"></a>Замечания  
 **sp_replflush** используется в репликации транзакций.  
  
 Определения статей сохраняются в кэше с целью повышения эффективности. **sp_replflush** используется другими хранимыми процедурами репликации при каждом изменении или удалении определения статьи.  
  
 Только одно соединение с клиентом может иметь доступ к данной базе данных для чтения журнала. Если клиент имеет доступ к базе данных для чтения журнала, выполнение **sp_replflush** заставляет клиента освободить доступ. Другие клиенты могут затем сканировать журнал транзакций с помощью **sp_replcmds** или **sp_replshowcmds**.  
  
## <a name="permissions"></a>Разрешения  
 Только члены предопределенной роли сервера **sysadmin** или предопределенной роли базы данных **db_owner** могут выполнять **sp_replflush**.  
  
## <a name="see-also"></a>См. также:  
 [sp_replcmds (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-replcmds-transact-sql.md)   
 [sp_repldone &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-repldone-transact-sql.md)   
 [sp_repltrans &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-repltrans-transact-sql.md)   
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
