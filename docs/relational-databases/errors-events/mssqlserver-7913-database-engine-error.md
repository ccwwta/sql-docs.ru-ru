---
description: MSSQLSERVER_7913
title: MSSQLSERVER_7913 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 7913 (Database Engine error)
ms.assetid: 9d8ad456-b1a2-4f79-a252-657fbec9ad9b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8d155cd7c5630e99e6fc6ece6f936584782a81f6
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99197736"
---
# <a name="mssqlserver_7913"></a>MSSQLSERVER_7913
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|7913|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|DBCC2_REPAIR_EXTENT_DEALLOCATED|  
|Текст сообщения|Исправление: выделение экстента P_ID отменено для объекта с идентификатором O_ID, индекса с идентификатором I_ID, секции с идентификатором PN_ID, единицы размещения с идентификатором A_ID (тип TYPE).|  
  
## <a name="explanation"></a>Объяснение  
Это информационное сообщение функции REPAIR, которое означает, что указанный объект был удален из экстента.  
  
## <a name="user-action"></a>Действие пользователя  
None  
  
