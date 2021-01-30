---
description: Ограничения инструкции DELETE
title: Ограничения инструкции DELETE | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- DELETE statement limitations [ODBC]
- ODBC SQL grammar, DELETE statement limitations
ms.assetid: 084761fe-e65b-4f38-ba4f-69884b2a7700
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: b188d782f82e23d031b820bba5f56a30dad414bd
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99181585"
---
# <a name="delete-statement-limitations"></a>Ограничения инструкции DELETE
Инструкция DELETE не поддерживается для Microsoft Excel или текстового драйвера. Обратите внимание, что инструкция INSERT поддерживается для текстового драйвера.  
  
 Драйвер dBASE не поддерживает упаковку таблиц для удаления "удаленных" значений.  
  
 Чтобы драйвер Paradox удалил строку из таблицы, таблица должна иметь уникальный индекс (первичный ключ Paradox).
