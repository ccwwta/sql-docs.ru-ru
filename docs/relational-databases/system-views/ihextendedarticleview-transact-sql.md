---
description: IHextendedArticleView (Transact-SQL)
title: IHextendedArticleView (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
f1_keywords:
- IHextendedArticleView_TSQL
- IHextendedArticleView
dev_langs:
- TSQL
helpviewer_keywords:
- IHextendedArticleView view
ms.assetid: 19ef0a12-3214-4bb0-9c25-a665897e65a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: c91f65a94e0eb2699b4146d1bafdeebc0c4201d6
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99186203"
---
# <a name="ihextendedarticleview-transact-sql"></a>IHextendedArticleView (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Представление **IHextendedArticleView** предоставляет сведения о статьях в публикации, отличной от SQL Server. Это представление хранится в базе данных **распространителя** .  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**publisher_id**|**smallint**|Уникальный идентификатор издателя.|  
|**publication_id**|**int**|Уникальный идентификатор публикации.|  
|**статья**|**sysname**|Имя статьи.|  
|**destination_object**|**sysname**|Имя объекта, опубликованного на стороне подписчика.|  
|**source_owner**|**sysname**|Владелец объекта, опубликованного на стороне издателя.|  
|**source_object**|**sysname**|Имя объекта, опубликованного на стороне издателя.|  
|**description**|**nvarchar(255)**|Описание статьи.|  
|**creation_script**|**nvarchar(255)**|Скрипт создания схемы для статьи.|  
|**del_cmd**|**nvarchar(255)**|Команда, выполняемая для инструкции DELETE.|  
|**filter**|**int**|Идентификатор хранимой процедуры, с помощью которого определяется горизонтальная секция.|  
|**filter_clause**|**ntext**|Предложение WHERE, которое применяется для горизонтальной фильтрации статьи.|  
|**ins_cmd**|**nvarchar(255)**|Команда, выполняемая для инструкции INSERT.|  
|**pre_creation_cmd**|**tinyint**|Команда, выполняемая перед инструкциями DROP TABLE, DELETE TABLE или TRUNCATE:<br /><br /> **0** = нет.<br /><br /> **1** = удалить.<br /><br /> **2** = удалить.<br /><br /> **3** = усечение.|  
|**status**|**tinyint**|Битовая маска параметров и состояния статьи, которая может быть результатом операции побитового логического ИЛИ над одним или несколькими из следующих значений:<br /><br /> **1** = статья активна.<br /><br /> **8** = включить имя столбца в инструкции INSERT.<br /><br /> **16** = использовать параметризованные инструкции.<br /><br /> **24** = оба значения включают имя столбца в инструкции INSERT и используют параметризованные инструкции.<br /><br /> Например, активная статья, использующая параметризованные инструкции, будет иметь значение **17** в этом столбце. Значение **0** означает, что статья неактивна и дополнительные свойства не определены.|  
|**type**|**tinyint**|Тип статьи:<br /><br /> **1** = статья на основе журнала.<br /><br /> **3** = статья на основе журнала с ручным фильтром.<br /><br /> **5** = статья на основе журнала с ручным просмотром.<br /><br /> **7** = статья на основе журнала с ручным фильтром и ручным просмотром.|  
|**upd_cmd**|**nvarchar(255)**|Команда, выполняемая для инструкции UPDATE.|  
|**schema_option**|**binary**|Указывает, что должно быть включено в скрипт. Список поддерживаемых параметров схемы см. в разделе [sp_addarticle &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addarticle-transact-sql.md) .|  
|**dest_owner**|**sysname**|Владелец объекта, опубликованного в целевой базе данных.|  
  
## <a name="see-also"></a>См. также  
 [Разнородная репликация базы данных](../../relational-databases/replication/non-sql/heterogeneous-database-replication.md)   
 [Таблицы репликации &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Представления репликации (Transact-SQL)](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
