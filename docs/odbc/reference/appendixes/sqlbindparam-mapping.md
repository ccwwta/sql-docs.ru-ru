---
description: Сопоставление SQLBindParam
title: Сопоставление Склбиндпарам | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- SQLBindparam function [ODBC], mapping
- mapping deprecated functions [ODBC], SQLBindParam
ms.assetid: 375f8f24-36de-4946-916e-c75abc6f070d
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 62951dc5ae69e86eb5cbc2fba21407d63952e74b
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99202935"
---
# <a name="sqlbindparam-mapping"></a>Сопоставление SQLBindParam
**Склбиндпарам** нельзя выключать как устаревший, так как он никогда не СУЩЕСТВОВАЛ в ODBC; Однако он по-прежнему представляет собой дублирующуюся функциональность. диспетчеру драйверов необходимо экспортировать его, так как ISO и открытые приложения, соответствующие группам, будут использовать его. Поскольку **SQLBindParameter** содержит все функции **склбиндпарам**, **Склбиндпарам** будет сопоставляться с **SQLBindParameter** (если базовый драйвер является драйвером ODBC *3. x* ). Драйверу ODBC *3. x* не требуется реализовывать **склбиндпарам**.  
  
## <a name="remarks"></a>Замечания  
 При следующем вызове **склбиндпарам** :  
  
```  
SQLBindParam(   StatementHandle,    ParameterNumber,    ValueType,    ParameterType,    ColumnSize,    DecimalDigits,    ParameterValuePtr,    StrLen_or_IndPtr)  
```  
  
 Диспетчер драйверов вызывает **SQLBindParameter** в драйвере следующим образом:  
  
```  
SQLBindParameter(   StatementHandle,    ParameterNumber,    SQL_PARAM_INPUT,    ValueType,    ParameterType,    ColumnSize,    DecimalDigits,    ParameterValuePtr,    BufferLength,    StrLen_or_IndPtr)  
```  
  
 Если приложение будет работать в 64-разрядной операционной системе, см. [сведения о ODBC 64-bit](../../../odbc/reference/odbc-64-bit-information.md).  
  
## <a name="see-also"></a>См. также:  
 [Сопоставление нерекомендуемых функций](../../../odbc/reference/appendixes/mapping-deprecated-functions.md)
