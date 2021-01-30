---
description: MSsnapshotdeliveryprogress (Transact-SQL)
title: MSsnapshotdeliveryprogress (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
f1_keywords:
- MSsnapshotdeliveryprogress_TSQL
- MSsnapshotdeliveryprogress
dev_langs:
- TSQL
helpviewer_keywords:
- MSsnapshotdeliveryprogress system table
ms.assetid: 9164bfe2-6fc4-4b52-946a-09ea3cf67041
author: cawrites
ms.author: chadam
ms.openlocfilehash: 1ff258550fb6954c2138326c440c68a0f1ad88b3
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99192313"
---
# <a name="mssnapshotdeliveryprogress-transact-sql"></a>MSsnapshotdeliveryprogress (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Таблица **MSsnapshotdeliveryprogress** используется для трассировки файлов, успешно доставленных подписчику при применении моментального снимка. Эти данные используются для возобновления доставки файлов в случае, если во время сеанса агент слияния не смог успешно доставить все файлы, чтобы те же самые файлы не доставлялись повторно при следующем запуске агента слияния. Эта таблица хранится на подписчике в базе данных подписки.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**session_token**|**nvarchar(260)**|Определяет путь к папке моментального снимка, откуда файл был успешно доставлен. Для публикаций, использующих параметризованные фильтры, строка **динснап** будет добавлена к значению.|  
|**progress_token_hash**|**int**|Хэш-значение, созданное на основе значения *progress_token* , которое используется для повышения эффективности поиска по заданному *progress_tokenому* значению.|  
|**progress_token**|**nvarchar (500)**|Определяет успешно доставленный файл; значение является сочетанием имени файла и пути.|  
|**progress_timestamp**|**datetime**|Значение **типа DateTime** , указывающее, когда файл моментального снимка был успешно доставлен.|  
  
## <a name="see-also"></a>См. также:  
 [Таблицы репликации &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Представления репликации (Transact-SQL)](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
