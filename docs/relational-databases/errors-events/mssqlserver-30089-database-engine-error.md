---
description: MSSQLSERVER_30089
title: MSSQLSERVER_30089 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 9992 (Database Engine error)
ms.assetid: 188e5bde-6865-4740-a2b2-582be8f55c77
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4f0832ea59b98a689bf2c6e876af41d72f048ef4
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99198188"
---
# <a name="mssqlserver_30089"></a>MSSQLSERVER_30089
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|30089|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|IFTS_FDHOST_TERMINATEDABNORMAL|  
|Текст сообщения|Процесс узла управляющей программы полнотекстовой фильтрации (FDHost) завершился аварийно. Причиной этого может быть неустранимая ошибка при полнотекстовом индексировании или обработке запроса, вызванная неверной настройкой или ошибкой в работе лингвистического компонента — средства разбиения по словам, парадигматического модуля или фильтра. Процесс будет перезапущен автоматически.|  
  
## <a name="explanation"></a>Объяснение  
На узле управляющей программы полнотекстовой фильтрации обнаружена какая-то проблема, которая привела к принудительному аварийному останову. Причиной проблемы может оказаться неправильно отформатированный документ, ошибка в фильтре или разделителе слов, а также нарушение в работе управляющей программы фильтрации.  
  
## <a name="user-action"></a>Действие пользователя  
Как правило, работа управляющей программы после подобной ошибки восстанавливается. Если же в процессе выполнения управляющей программы снова и снова происходит неуспешное завершение, необходимо устранение неполадок. Для выявления причин проблемы попробуйте выполнить следующие действия.  
  
1.  Если недавно установлен новый лингвистический компонент, удалите его из системы.  
  
2.  Просмотрите журнал сканирования, чтобы выявить какой-либо из новых документов, для которого не удалось провести полнотекстовую индексацию, и удалите его.  
  
## <a name="see-also"></a>См. также:  
[sp_help_fulltext_system_components (Transact-SQL)](~/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql.md)  
[Настройка и управление средством разбиения на слова и парадигматические модули для поиска](~/relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md)  
[Настройка и управление фильтрами для поиска](~/relational-databases/search/configure-and-manage-filters-for-search.md)  
  
