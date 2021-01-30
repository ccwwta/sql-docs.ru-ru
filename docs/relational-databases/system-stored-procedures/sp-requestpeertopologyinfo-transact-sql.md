---
description: sp_requestpeertopologyinfo (Transact-SQL)
title: sp_requestpeertopologyinfo (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
f1_keywords:
- sp_requestpeertopologyinfo
- sp_requestpeertopologyinfo_TSQL
helpviewer_keywords:
- sp_requestpeertopologyinfo
ms.assetid: 15cd28bd-5a72-41fb-ae1b-726baaa6fad5
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 5cd33688e4a3d5ba5f1b849580f9c180a1ad4d98
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99182055"
---
# <a name="sp_requestpeertopologyinfo-transact-sql"></a>sp_requestpeertopologyinfo (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Заполняет системную таблицу [MSpeer_topologyresponse](../../relational-databases/system-tables/mspeer-topologyresponse-transact-sql.md) сведениями о топологии одноранговой репликации транзакций. Выполните [sp_gettopologyinfo](../../relational-databases/system-stored-procedures/sp-gettopologyinfo-transact-sql.md) , чтобы получить сведения из таблицы в формате XML.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_requestpeertopologyinfo [ @publication = ] 'publication'  
        [ ,[ @requestid=] request_id OUTPUT  
```  
  
## <a name="arguments"></a>Аргументы  
 [ @publication =] "*Публикация*"  
 Имя публикации, для которой должен быть выполнен запрос состояния всей топологии. Аргумент *publication* имеет тип **sysname** и не имеет значения по умолчанию.  
  
 [ @request_id =] *request_id*  
 Идентификатор, назначенный запросу состояния топологии. *request_id* имеет **тип int** и значение по умолчанию NULL. Этот идентификатор может использоваться [sp_gettopologyinfo](../../relational-databases/system-stored-procedures/sp-gettopologyinfo-transact-sql.md).  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (сбой)  
  
## <a name="remarks"></a>Замечания  
 Процедура sp_requestpeertopologyinfo используется в одноранговой репликации транзакций. Перед выполнением [sp_gettopologyinfo](../../relational-databases/system-stored-procedures/sp-gettopologyinfo-transact-sql.md)выполните sp_requestpeertopologyinfo. Эти процедуры используются мастером настройки одноранговой топологии, однако ими можно также воспользоваться напрямую, если необходимо получить сведения о топологии в формате XML. Если вы предпочитаете табличные результаты, запросите системную таблицу [MSpeer_topologyresponse](../../relational-databases/system-tables/mspeer-topologyresponse-transact-sql.md) .  
  
## <a name="permissions"></a>Разрешения  
 Необходимо членство в предопределенной роли сервера sysadmin или предопределенной роли базы данных db_owner.  
  
## <a name="see-also"></a>См. также:  
 [Одноранговая репликация транзакций](../../relational-databases/replication/transactional/peer-to-peer-transactional-replication.md)   
 [Хранимые процедуры репликации (Transact-SQL)](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)  
  
  
