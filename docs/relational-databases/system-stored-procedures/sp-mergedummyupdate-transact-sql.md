---
description: sp_mergedummyupdate (Transact-SQL)
title: sp_mergedummyupdate (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
f1_keywords:
- sp_mergedummyupdate_TSQL
- sp_mergedummyupdate
helpviewer_keywords:
- sp_mergedummyupdate
ms.assetid: b834f7f6-9588-4d59-a3e2-83d8e8e722e1
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 7c64a3acd9dae0797a70ed8c167010f2d32479b2
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99185290"
---
# <a name="sp_mergedummyupdate-transact-sql"></a>sp_mergedummyupdate (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Производит фиктивное обновление данной строки, чтобы вновь переслать ее в ходе следующего объединения. Эта хранимая процедура может выполняться на издателе в базе данных публикации или на подписчике в базе данных подписки.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_mergedummyupdate [ @source_object =] 'source_object', [ @rowguid =] 'rowguid'  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @source_object = ] 'source_object'` Имя исходного объекта. *source_object* имеет тип **nvarchar (386)** и не имеет значения по умолчанию.  
  
`[ @rowguid = ] 'rowguid'` Идентификатор строки. *rowguid* имеет тип **uniqueidentifier** и не имеет значения по умолчанию.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (сбой)  
  
## <a name="remarks"></a>Замечания  
 **sp_mergedummyupdate** используется в репликации слиянием.  
  
 **sp_mergedummyupdate** удобно использовать при написании собственной альтернативы средство просмотра конфликтов репликации (Wzcnflct.exe).  
  
## <a name="permissions"></a>Разрешения  
 Только члены предопределенной роли базы данных **db_owner** могут выполнять **sp_mergedummyupdate**.  
  
## <a name="see-also"></a>См. также:  
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
