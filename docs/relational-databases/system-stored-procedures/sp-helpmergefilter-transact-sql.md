---
description: Хранимая процедура sp_helpmergefilter (Transact-SQL)
title: sp_helpmergefilter (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
f1_keywords:
- sp_helpmergefilter
- sp_helpmergefilter_TSQL
helpviewer_keywords:
- sp_helpmergefilter
ms.assetid: f133a094-0009-4771-b93b-e86a5c01e40b
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 862f23713da4bcd611310149b509e34658766006
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99179239"
---
# <a name="sp_helpmergefilter-transact-sql"></a>Хранимая процедура sp_helpmergefilter (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Возвращает сведения о фильтрах слияния. Эта хранимая процедура выполняется на подписчике в любой базе данных.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_helpmergefilter [ @publication= ] 'publication'   
    [ , [ @article= ] 'article']  
    [ , [ @filtername= ] 'filtername']  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @publication = ] 'publication'` Имя публикации. Аргумент *publication* имеет тип **sysname** и не имеет значения по умолчанию.  
  
`[ @article = ] 'article'` Имя статьи. Аргумент *article* имеет тип **sysname** и значение по умолчанию **%** , которое возвращает имена всех статей.  
  
`[ @filtername = ] 'filtername'` Имя фильтра, сведения о котором возвращаются. *filtername* имеет тип **sysname** и значение по умолчанию **%** , которое возвращает сведения обо всех фильтрах, определенных для статьи или публикации.  
  
## <a name="result-sets"></a>Результирующие наборы  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**join_filterid**|**int**|Идентификатор фильтра соединения.|  
|**filtername**|**sysname**|Имя фильтра.|  
|**join article name**|**sysname**|Имя статьи соединения.|  
|**join_filterclause**|**nvarchar (2000)**|Выражение фильтра для уточнения соединения.|  
|**join_unique_key**|**int**|Определяет, производится ли соединение по уникальному ключу.|  
|**base table owner**|**sysname**|Имя владельца базовой таблицы.|  
|**base table name**|**sysname**|Имя базовой таблицы.|  
|**join table owner**|**sysname**|Имя владельца таблицы, соединяемой с основной таблицей.|  
|**join table name**|**sysname**|Имя таблицы, соединяемой с основной таблицей.|  
|**article name**|**sysname**|Имя статьи таблицы, соединяемой с основной таблицей.|  
|**filter_type**|**tinyint**|Тип фильтра слияния. Может быть одним из следующих:<br /><br /> **1** = только фильтр объединения<br /><br /> **2** = связь логических записей<br /><br /> **3** = оба|  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (сбой)  
  
## <a name="remarks"></a>Замечания  
 **sp_helpmergefilter** используется в репликации слиянием.  
  
## <a name="permissions"></a>Разрешения  
 Только члены предопределенной роли сервера **sysadmin** и **db_owner** предопределенной роли базы данных могут выполнять **sp_helpmergefilter**.  
  
## <a name="see-also"></a>См. также:  
 [sp_addmergefilter (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-addmergefilter-transact-sql.md)   
 [sp_changemergefilter (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-changemergefilter-transact-sql.md)   
 [sp_dropmergefilter (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-dropmergefilter-transact-sql.md)   
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
