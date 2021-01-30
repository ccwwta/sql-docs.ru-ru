---
description: Ограничения инструкции ALTER TABLE
title: Ограничения инструкции ALTER TABLE | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- ODBC SQL grammar, ALTER TABLE statement limitations
- ALTER TABLE statement limitations [ODBC]
ms.assetid: f3e88f85-edf4-47cd-a822-292b106ddb34
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: d36e5dfb2457a9d3453dbe3bc877c5d267731ea1
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99205744"
---
# <a name="alter-table-statement-limitations"></a>Ограничения инструкции ALTER TABLE
Если используется драйвер dBASE или Paradox, то после создания индекса и добавления новой записи структура таблицы не может быть изменена инструкцией ALTER TABLE, если только индекс не будет удален и не будет удалено содержимое таблицы.  
  
 Инструкции ALTER TABLE не поддерживаются для Microsoft Excel или текстовых драйверов.  
  
> [!NOTE]  
>  При использовании драйвера Paradox без реализации ядро СУБД Borland инструкции ALTER TABLE не поддерживаются. допускаются только инструкции Read и Append.
