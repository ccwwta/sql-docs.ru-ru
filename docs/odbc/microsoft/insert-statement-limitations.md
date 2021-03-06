---
description: Ограничения инструкции INSERT
title: Ограничения инструкции INSERT | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- ODBC SQL grammar, INSERT statement limitations
- INSERT statement limitations [ODBC]
- truncation of data [ODBC]
ms.assetid: dea05698-527a-41ab-8729-bbed85556185
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: c8decef6ed2a17a2aca4b107d46b856b6ba828a4
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99211191"
---
# <a name="insert-statement-limitations"></a>Ограничения инструкции INSERT
Вставленные данные усекаются справа без предупреждения, если они слишком длинные для размещения в столбце.  
  
 Попытка вставить значение, находящийся вне диапазона типа данных столбца, приводит к вставке значения NULL в столбец.  
  
 При использовании dBASE, Microsoft Excel, Paradox или Текстдривер Вставка строки нулевой длины в столбец фактически вставляет значение NULL.  
  
 При использовании драйвера Microsoft Excel, если в столбец вставляется пустая строка, то пустая строка преобразуется в NULL. Поисковая инструкция SELECT, которая выполняется с пустой строкой в предложении WHERE, не будет выполнена для этого столбца.  
  
 Таблица не может обновляться драйвером Paradox при выполнении двух условий:  
  
-   Если для таблицы не определен уникальный индекс. Это не верно для пустой таблицы, которую можно обновить с помощью одной строки, даже если для таблицы не определен уникальный индекс. Если одна строка вставляется в пустую таблицу, которая не имеет уникального индекса, приложение не может создать уникальный индекс или вставить дополнительные данные после вставки одной строки.  
  
-   Если ядро СУБД Borland не реализована, в таблице Paradox разрешены только инструкции Read и Append.  
  
 При использовании текстового драйвера значения NULL представляются в виде пустой строки в файлах фиксированной длины, но не представлены пробелами в файлах с разделителями. Например, в следующей строке, содержащей три поля, второе поле имеет значение NULL:  
  
```  
"Smith:,, 123  
```  
  
 При использовании текстового драйвера все значения столбцов могут быть дополнены начальными пробелами. Длина любой строки должна быть меньше или равна 65 543 байт.
