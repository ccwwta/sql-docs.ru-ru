---
description: MSSQLSERVER_12329
title: MSSQLSERVER_12329 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 12329 (Database Engine error)
ms.assetid: 43f90287-36d5-46c2-ac91-a37202dcf6d3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73c58c5c97f71ed355f476bd5395197d5f0b0af1
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99197062"
---
# <a name="mssqlserver_12329"></a>MSSQLSERVER_12329
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|12329|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|HK_UNSUPPORTED_NON_LATIN_CODEPAGE|  
|Текст сообщения|Типы данных char(n) и varchar(n) с параметрами сортировки, кодовая страница которых отлична от 1252, не поддерживаются *конструкцией*.|  
  
## <a name="explanation"></a>Объяснение  
Не используйте типы данных char(n) и varchar(n) с параметрами сортировки, кодовая страница которых отлична от 1252.  
  
## <a name="user-action"></a>Действие пользователя  
Одна непредвиденная ситуация, которая может привести к формированию этой ошибки:  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = 'us_english')  
```  
  
Вместо этого используйте:  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
```  
  
