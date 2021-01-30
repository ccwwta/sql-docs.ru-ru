---
description: Сопоставление SQLSetParam
title: Сопоставление SQLSetParam | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- mapping deprecated functions [ODBC], SQLSetParam
- SQLSetParam function [ODBC], mapping
ms.assetid: 022dfbc0-8d18-4c35-8a28-d9eb16063188
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 6e2488c689a4da1152e115017287274252c6b405
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99202624"
---
# <a name="sqlsetparam-mapping"></a>Сопоставление SQLSetParam
**SQLSetParam** по **SQLBindParameter** , как в ODBC 2, будет продолжать сопоставляться. *x*. Несмотря на то, что концептуально похоже на **склбиндпарам**, диспетчер драйверов не сопоставляет **SQLSetParam** с **склбиндпарам**. Это связано с тем, что некоторые существующие ODBC 2. драйверы *x* используют специальное значение *BufferLength* (SQL_SETPARAM_VALUE_MAX), которое диспетчер драйверов создает при сопоставлении **SQLSetParam** поверх **SQLBindParameter** , чтобы определить, когда он вызывается с помощью 1. Приложение *x* ODBC.  
  
 Вызов метода  
  
```  
SQLSetParam(hstmt, ipar, fCType, fSqlType, cbColDef, ibScale, rgbValue, pcbValue)  
```  
  
 приведет к следующему результату:  
  
```  
SQLBindParameter(StatementHandle, ParameterNumber, SQL_PARAM_INPUT_OUTPUT, ValueType, ParameterType, ColumnSize, DecimalDigits, ParameterValuePtr, SQL_SETPARAM_VALUE_MAX, StrLen_or_IndPtr)  
```
