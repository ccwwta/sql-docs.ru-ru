---
description: MSSQLSERVER_2538
title: MSSQLSERVER_2538 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 2538 (Database Engine error)
ms.assetid: 0a0f7d79-f1ba-4749-8804-fb660cca3492
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e9a3a8f8de34d81209719fc0e8a17b89b4b68268
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99181028"
---
# <a name="mssqlserver_2538"></a>MSSQLSERVER_2538
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|2538|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|DBCC_ALLOCATION_SUMMARY_PER_FILE|  
|Текст сообщения|Файл FILE. Число экстентов = EXTENTS, использованных страниц = USED_PAGES, зарезервированных страниц = RESERVED_PAGES.|  
  
## <a name="explanation"></a>Объяснение  
Эти сведения являются частью выходных данных команды DBCC CHECKALLOC. Это сведения являются сводкой для каждого файла о размещенных экстентах, использованных и зарезервированных страницах указанной базы данных.  
  
## <a name="user-action"></a>Действие пользователя  
None  
  
