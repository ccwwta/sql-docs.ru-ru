---
description: sp_helparticlecolumns (Transact-SQL)
title: sp_helparticlecolumns (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
f1_keywords:
- sp_helparticlecolumns
- sp_helparticlecolumns_TSQL
helpviewer_keywords:
- sp_helparticlecolumns
ms.assetid: 9ea55df3-2e99-4683-88ad-bde718288bc7
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 96e4f5508af16314312d2add0a7cdb8dd07a3921
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99176475"
---
# <a name="sp_helparticlecolumns-transact-sql"></a>sp_helparticlecolumns (Transact-SQL)
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

  Возвращает все столбцы базовой таблицы. Эта хранимая процедура выполняется на издателе в базе данных публикации. Для издателей Oracle данная хранимая процедура выполняется распространителем для любой базы данных.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_helparticlecolumns [ @publication = ] 'publication'   
        , [ @article = ] 'article'  
    [ , [ @publisher = ] 'publisher' ]  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @publication = ] 'publication'` Имя публикации, содержащей статью. Аргумент *publication* имеет тип **sysname** и не имеет значения по умолчанию.  
  
`[ @article = ] 'article'` Имя статьи, для которой возвращены столбцы. Аргумент *article* имеет тип **sysname** и не имеет значения по умолчанию.  
  
`[ @publisher = ] 'publisher'` Указывает издателя, отличного от [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Аргумент *Publisher* имеет тип **sysname** и значение по умолчанию NULL.  
  
> [!NOTE]  
>  не следует указывать *Издатель* , если запрошенная статья опубликована [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] издателем.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (неопубликованные столбцы) или **1** (опубликованные столбцы)  
  
## <a name="result-sets"></a>Результирующие наборы  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**Идентификатор столбца**|**int**|Идентификатор столбца.|  
|**column**|**sysname**|Имя столбца.|  
|**выпущен**|**bit**|Опубликован ли столбец:<br /><br /> **0** = Нет<br /><br /> **1** = Да|  
|**тип издателя**|**sysname**|Тип данных столбца на издателе.|  
|**Тип подписчика**|**sysname**|Тип данных столбца на подписчике.|  
  
## <a name="remarks"></a>Замечания  
 **sp_helparticlecolumns** используется в моментальных снимках и репликации транзакций.  
  
 **sp_helparticlecolumns** удобно использовать для проверки вертикальной секции.  
  
## <a name="permissions"></a>Разрешения  
 Только члены предопределенной роли сервера **sysadmin** , предопределенной роли базы данных **db_owner** или списка доступа к публикации для текущей публикации могут выполнять **sp_helparticlecolumns**.  
  
## <a name="see-also"></a>См. также:  
 [Определение и изменение фильтра столбцов](../../relational-databases/replication/publish/define-and-modify-a-column-filter.md)   
 [sp_addarticle &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addarticle-transact-sql.md)   
 [sp_articlecolumn (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-articlecolumn-transact-sql.md)   
 [sp_changearticle (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-changearticle-transact-sql.md)   
 [sp_droparticle (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-droparticle-transact-sql.md)   
 [sp_droppublication &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-droppublication-transact-sql.md)   
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
