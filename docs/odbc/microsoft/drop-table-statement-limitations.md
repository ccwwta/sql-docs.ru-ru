---
description: Ограничения инструкции DROP TABLE
title: Ограничения инструкции DROP TABLE | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- ODBC SQL grammar, DROP TABLE statement limitations
- DROP TABLE statement limitations [ODBC]
ms.assetid: 0a1c80f5-c9f2-4655-9bfd-0131b2f015a9
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: ac99015ec033aaad32a3e775646fed4fd3cb12ed
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99192609"
---
# <a name="drop-table-statement-limitations"></a>Ограничения инструкции DROP TABLE
При использовании драйвера Microsoft Excel 5,0, 7,0 или 97 инструкция DROP TABLE очищает лист, но не удаляет имя листа. Так как имя листа по-прежнему существует в книге, нельзя создать другой лист с таким же именем.
