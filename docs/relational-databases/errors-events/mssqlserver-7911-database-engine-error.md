---
description: MSSQLSERVER_7911
title: MSSQLSERVER_7911 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 7911 (Database Engine error)
ms.assetid: dd8390f3-0f77-4fb2-ba94-631a56e42bc6
author: MashaMSFT
ms.author: mathoma
robots: noindex,nofollow
ms.openlocfilehash: 5fe814cb9eb29e59e2ed10d5f820bc148997b5ea
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99210534"
---
# <a name="mssqlserver_7911"></a>MSSQLSERVER_7911
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|7911|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|DBCC2_REPAIR_PAGE_DEALLOCATED|  
|Текст сообщения|Исправление: отменено выделение страницы P_ID объекту с идентификатором O_ID, идентификатором индекса I_ID, идентификатором секции PN_ID, идентификатором единицы распределения A_ID (тип TYPE).|  
  
## <a name="explanation"></a>Объяснение  
Это информационное сообщение инструкции REPAIR, указывающее, что страница была освобождена из карты распределения индекса (IAM)-страницы.  
  
## <a name="user-action"></a>Действие пользователя  
None  
  
