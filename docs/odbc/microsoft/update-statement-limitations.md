---
description: Ограничения инструкции UPDATE
title: Ограничения инструкции UPDATE | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- UPDATE statement limitations [ODBC]
- ODBC SQL grammar, UPDATE statement limitations
ms.assetid: 14700aac-e135-4dc0-9138-4b01224461d5
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 721af98991f4d63c459ba5df44bc425c245d2dc7
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99190626"
---
# <a name="update-statement-limitations"></a>Ограничения инструкции UPDATE
Чтобы драйвер Paradox имел возможность обновить таблицу, таблица должна иметь уникальный индекс (первичный ключ Paradox). При использовании драйвера Paradox без реализации ядро СУБД Borland обновление таблицы Paradox невозможно.  
  
 Не поддерживается драйвером текста.  
  
 При использовании драйвера Microsoft Excel можно обновить значения, но нельзя удалить строку из таблицы, основанной на электронной таблице Microsoft Excel. В результате инструкция UPDATE не считается официально поддерживаемой драйвером Microsoft Excel. Поддерживается только инструкция INSERT.
