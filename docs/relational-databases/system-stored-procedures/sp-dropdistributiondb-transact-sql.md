---
title: sp_dropdistributiondb (Transact-SQL) | Документация Майкрософт
description: Удаляет базу данных распространителя и используемые ею файлы, если они не используются другой базой данных. Эта хранимая процедура выполняется на распространителе в любой базе данных.
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
f1_keywords:
- sp_dropdistributiondb_TSQL
- sp_dropdistributiondb
helpviewer_keywords:
- sp_dropdistributiondb
ms.assetid: b6dd1846-2259-4d29-93af-a70a5d25a0c5
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 2de544361c4bcd9befb80e5172e0b4887a984a9d
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99191196"
---
# <a name="sp_dropdistributiondb-transact-sql"></a>sp_dropdistributiondb (Transact-SQL)
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

  Сбрасывает базу данных распространителя. Сбрасывает физические файлы, используемые базой данных, если они не используются другой базой данных. Эта хранимая процедура выполняется на распространителе в любой базе данных.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_dropdistributiondb [ @database= ] 'database'  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @database = ] 'database'` Удаляемая база данных. Аргумент *Database* имеет тип **sysname** и не имеет значения по умолчанию.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (сбой)  
  
## <a name="remarks"></a>Замечания  
 **sp_dropdistributiondb** используется во всех типах репликации.  
  
 Эту хранимую процедуру необходимо выполнить перед удалением распространителя, выполнив **sp_dropdistributor**.  
  
 **sp_dropdistributiondb** также удаляет задание агент чтения очереди для базы данных распространителя, если оно существует.  
  
 Чтобы отключить распространение, база данных распространителя должна быть в режиме «в сети». Если для базы данных распространителя существует моментальный снимок базы данных, он должен быть сброшен перед отключением распространения. Моментальный снимок базы данных доступен только для чтения в виде копии базы данных вне сети и не относится к моментальному снимку репликации. Дополнительные сведения см. в разделе [Моментальные снимки базы данных (SQL Server)](../../relational-databases/databases/database-snapshots-sql-server.md).  
  
## <a name="example"></a>Пример  
 [!code-sql[HowTo#sp_DropDistPub](../../relational-databases/replication/codesnippet/tsql/sp-dropdistributiondb-tr_1.sql)]  
  
## <a name="permissions"></a>Разрешения  
 Только члены предопределенной роли сервера **sysadmin** могут выполнять **sp_dropdistributiondb**.  
  
## <a name="see-also"></a>См. также:  
 [Disable Publishing and Distribution](../../relational-databases/replication/disable-publishing-and-distribution.md)  (Отключение публикации и распространения)  
 [sp_adddistributiondb &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-adddistributiondb-transact-sql.md)   
 [sp_changedistributiondb &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-changedistributiondb-transact-sql.md)   
 [sp_helpdistributiondb (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-helpdistributiondb-transact-sql.md)   
 [Хранимые процедуры репликации (Transact-SQL)](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)  
  
  
