---
description: Переопределение заданных по умолчанию точности и шкалы для числовых типов данных
title: Переопределение точности и масштаба по умолчанию для числовых типов данных | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- numeric data type [ODBC], precision and scale
- precision [ODBC], numeric data types
- data types [ODBC], numeric data types
- numeric data type [ODBC]
- numeric literals [ODBC]
ms.assetid: 84292334-0e33-4a1b-84de-8c018dd787f3
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 007df3acd040b3b227563c84eb68c0de495f0aef
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99194795"
---
# <a name="overriding-default-precision-and-scale-for-numeric-data-types"></a>Переопределение заданных по умолчанию точности и шкалы для числовых типов данных
Если поле SQL_DESC_TYPE в АРД имеет значение SQL_C_NUMERIC, вызывая либо **SQLBindCol** , либо **SQLSetDescField**, поле SQL_DESC_SCALE в АРД имеет значение 0, а в поле SQL_DESC_PRECISION задана точность по умолчанию, определенная драйвером. Это также справедливо, если поле SQL_DESC_TYPE в APD имеет значение SQL_C_NUMERIC, вызывая либо **SQLBindParameter** , либо **SQLSetDescField**. Это справедливо для входных, входных и выходных параметров.  
  
 Если одно из описанных выше значений по умолчанию неприемлемо для приложения, приложение должно задать SQL_DESC_SCALE или SQL_DESC_PRECISION поле, вызвав **SQLSetDescField** или **SQLSetDescRec**.  
  
 Если приложение вызывает **SQLGetData** для возврата данных в структуру SQL_C_NUMERIC, используются поля SQL_DESC_SCALE и SQL_DESC_PRECISION по умолчанию. Если значения по умолчанию неприемлемы, приложение должно вызвать **SQLSetDescRec** или **SQLSetDescField** , чтобы задать поля, а затем вызвать **SQLGetData** с *TargetType* SQL_ARD_TYPE для использования значений в полях дескриптора.  
  
 При вызове **SQLPutData** в вызове используются поля SQL_DESC_SCALE и SQL_DESC_PRECISION записи дескриптора, которые соответствуют параметру или столбцу, который используется для данных во время выполнения, которые являются полями APD для вызовов **SQLExecute** или **SQLExecDirect** или поля АРД для вызовов **SQLBulkOperations** или **SQLSetPos**.
