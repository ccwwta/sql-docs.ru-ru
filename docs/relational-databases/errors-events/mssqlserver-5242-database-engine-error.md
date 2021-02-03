---
description: MSSQLSERVER_5242
title: MSSQLSERVER_5242 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 5242 (Database Engine error)
ms.assetid: 712b1a10-2f87-41df-a111-1ed9f14102d4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 58ac27fac4af3c8d343102403549758ea428d494
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99198131"
---
# <a name="mssqlserver_5242"></a>MSSQLSERVER_5242
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|5242|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя||  
|Текст сообщения|В ходе выполнения внутренней операции в базе данных «%.*ls» (идентификатор: %d) на странице %S_PGID была обнаружена несогласованность. Обратитесь в службу технической поддержки. Номер ссылки %ld.|  
  
## <a name="explanation"></a>Объяснение  
На странице базы данных возникла несогласованность, на которую указывает сообщение об ошибке.  
  
## <a name="see-also"></a>См. также:  
[DBCC CHECKDB (Transact-SQL)](~/t-sql/database-console-commands/dbcc-checkdb-transact-sql.md)  
[Файлы и файловые группы базы данных](~/relational-databases/databases/database-files-and-filegroups.md)  
  
