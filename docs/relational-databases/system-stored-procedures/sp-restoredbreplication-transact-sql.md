---
description: sp_restoredbreplication (Transact-SQL)
title: sp_restoredbreplication (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
f1_keywords:
- sp_restoredbreplication
- sp_restoredbreplication_TSQL
helpviewer_keywords:
- sp_restoredbreplication
ms.assetid: a2c5ee32-e6d9-46e9-8031-8ff13c20acf7
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 841a162c9619344fa297951277642f306d8539ed
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99194374"
---
# <a name="sp_restoredbreplication-transact-sql"></a>sp_restoredbreplication (Transact-SQL)
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

  Удаляет настройки репликации при восстановлении базы данных на сервер в базу данных, не являющиеся ее источниками, или на системе, не способной по какой-либо причине выполнять процессы репликации. При восстановлении реплицированной базы данных на сервер или в базу данных, отличающиеся от источника, с которого была создана резервная копия, сохранить настройки репликации невозможно. При восстановлении сервер вызывает **sp_restoredbreplication** напрямую для автоматического удаления метаданных репликации из восстановленной базы данных.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_restoredbreplication [ @srv_orig = ] 'original_server_name'  
        , [ @db_orig = ] 'original_database_name'  
    [ , [ @keep_replication = ] keep_replication ]  
    [ , [ @perform_upgrade = ] perform_upgrade ]  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @srv_orig = ] 'original_server_name'`  
 Возвращает имя сервера, на котором была создана резервная копия. Аргумент *original_server_name* имеет тип **sysname** и не имеет значения по умолчанию.  
  
`[ @db_orig = ] 'original_database_name'`  
 Имя базы данных, резервная копия которой была сделана. Аргумент *original_database_name* имеет тип **sysname** и не имеет значения по умолчанию.  
  
`[ @keep_replication = ] keep_replication`  
 [!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]  
  
`[ @perform_upgrade = ] perform_upgrade`  
 [!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (сбой)  
  
## <a name="remarks"></a>Замечания  
 **sp_restoredbreplication** используется во всех типах репликации.  
  
## <a name="permissions"></a>Разрешения  
 Только члены предопределенной роли сервера **sysadmin** или **dbcreator** или схемы базы данных **dbo** могут выполнять **sp_restoredbreplication**.  
  
## <a name="see-also"></a>См. также:  
 [Хранимые процедуры репликации (Transact-SQL)](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)  
  
  
