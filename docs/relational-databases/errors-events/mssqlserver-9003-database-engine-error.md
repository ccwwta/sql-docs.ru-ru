---
description: MSSQLSERVER_9003
title: MSSQLSERVER_9003 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 9003 (Database Engine error)
ms.assetid: 7fdfb391-5c6f-428b-b434-6c3d0b30fd7b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 37070cdc53894b703674e4bd696cd162796351fa
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99161976"
---
# <a name="mssqlserver_9003"></a>MSSQLSERVER_9003
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|9003|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|LOG_INVALID_LSN|  
|Текст сообщения|Передан недопустимый номер %S_LSN для просмотра журнала в базе данных «%.*ls». Эта ошибка может свидетельствовать о повреждении данных или о том, что файл журнала (LDF) не соответствует файлу данных (MDF). Если она возникла во время репликации, повторно создайте публикацию. В противном случае, если ошибка приводит к сбою при загрузке, произведите восстановление из резервной копии.|  
  
## <a name="explanation"></a>Объяснение  
Компонент передал менеджеру журнала базы данных недопустимый регистрационный номер транзакции в журнале. Это может быть вызвано проблемами репликации, повреждением данных или несоответствием между первичным файлом данных и файлом журнала.  
  
## <a name="user-action"></a>Действие пользователя  
Если эта ошибка возникла во время репликации, повторно создайте публикацию. В противном случае выполните восстановление из резервной копии.  
  
