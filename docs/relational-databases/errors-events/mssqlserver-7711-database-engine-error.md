---
description: MSSQLSERVER_7711
title: MSSQLSERVER_7711 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 7711 (Database Engine error)
ms.assetid: a5c7cd6e-18d6-47ef-902b-db9dd64bba34
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9b6d42976c5fe7c55ac7b8505b055c3677fecacd
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99174774"
---
# <a name="mssqlserver_7711"></a>MSSQLSERVER_7711
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|7711|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|PRT_RANGE_OVERLAP|  
|Текст сообщения|Параметр DATA_COMPRESSION указан более одного раза для таблицы, индекса, либо одной из секций таблицы или индекса.|  
  
## <a name="explanation"></a>Объяснение  
В одной из следующих инструкций при обработке параметра DATA_COMPRESSION произошла ошибка.  
  
-   CREATE TABLE  
  
-   ALTER TABLE  
  
-   CREATE INDEX  
  
-   ALTER INDEX  
  
Если указанная таблица (или индекс) секционирована, то по крайней мере для одной из секций параметр DATA_COMPRESSION был указан более одного раза. Если указанная таблица (или индекс) не секционирована, то параметр DATA_COMPRESSION был указан более одного раза.  
  
## <a name="user-action"></a>Действие пользователя  
Применительно к секционированной таблице (индексу) убедитесь, что параметр DATA_COMPRESSION указан для каждой секции не более одного раза. Применительно к несекционированной таблице (индексу), указывайте параметр DATA_COMPRESSION в этой инструкции не более одного раза.  
  
