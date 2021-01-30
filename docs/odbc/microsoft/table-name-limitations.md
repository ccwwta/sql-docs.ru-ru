---
description: Ограничения имен таблиц
title: Ограничения имен таблиц | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- ODBC SQL grammar, table name limitations
- table name limitations [ODBC]
- Excel driver [ODBC], table name limitations
ms.assetid: d9843e4b-1d05-4d5a-9dc3-ee9ec59edb97
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 1b3a13919a20a8092c730ce3dfbe35358d1898df
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99182549"
---
# <a name="table-name-limitations"></a>Ограничения имен таблиц
Имена таблиц могут содержать любые допустимые символы (например, пробелы). Если имена таблиц содержат любые символы, кроме букв, цифр и знаков подчеркивания, имя должно быть заключено в кавычки (').  
  
 Если используется драйвер Microsoft Excel и имя таблицы не уточняется ссылкой на базу данных, подразумевается база данных по умолчанию. Если имя в Microsoft Excel содержит символ "!", он будет автоматически преобразован в символ "$".  
  
 Имя таблицы Microsoft Excel, на которое ссылаются, \<filename> поддерживается для файлов Microsoft excel 3,0 и 4,0. Имя таблицы Microsoft Excel, на которое ссылаются, \<workbook-name> поддерживается для файлов Microsoft excel 5,0, 7,0 или 97.  
  
 При использовании драйвера dBASE символы со значением ASCII, превышающим 127, преобразуются в знаки подчеркивания.  
  
 При использовании драйвера Microsoft Access длина имени таблицы ограничена 64 символами.  
  
 Если используется драйвер dBASE, Microsoft Excel 3,0 или 4,0, Paradox или Text, в качестве имен таблиц не следует использовать специальные ключевые слова MS-DOS CON, AUX, LPT1 и LPT2.
