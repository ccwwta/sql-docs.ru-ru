---
description: 64-разрядные целочисленные структуры
title: 64-разрядные целочисленные структуры | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- C data types [ODBC], 64-bit integer structures
- data types [ODBC], C data types
- 64-bit integer structures [ODBC]
ms.assetid: ac80c798-d9b2-4430-85ed-bd2461db0ac7
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: cda6c3bd7e1ad9e850d6c9bbb0c444e5bf3e5f5f
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99198165"
---
# <a name="64-bit-integer-structures"></a>64-разрядные целочисленные структуры
Тип C для SQL_C_SBIGINT и SQL_C_UBIGINT идентификаторы типов данных в компиляторах Microsoft C — это _int64. Если используется компилятор, отличный от компилятора Microsoft® C, тип C может отличаться. Если компилятор поддерживает 64-разрядные целые числа, то драйвер или приложение должны определить ODBCINT64 как собственный 64-разрядный целочисленный тип. Если компилятор не поддерживает 64-разрядные целые числа в собственном режиме, приложение или драйвер может определить следующие структуры, чтобы убедиться, что он имеет доступ к этим данным:  
  
```  
typedef struct{  
SQLUINTEGER dwLowWord;  
SQLUINTEGER dwHighWord;  
} SQLUBIGINT  
  
typedef struct{  
SQLUINTEGER dwLowWord;  
SQLINTEGER sdwHighWord;  
} SQLBIGINT  
```  
  
 Эти структуры должны быть согласованы с 8-байтовой границей, поскольку 64-разрядное целое число соответствует 8-байтной границе.
