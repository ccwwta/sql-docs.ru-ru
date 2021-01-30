---
description: Escape-последовательности GUID
title: Escape-последовательности GUID | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- ODBC escape sequences [ODBC], GUID
- escape sequences [ODBC], guid
- guid escape sequence [ODBC]
ms.assetid: 71d43ef9-4a31-493e-b9e0-f864e9ef3ce6
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 535d24034c219691b192d409f72df15c83ab22c7
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99208580"
---
# <a name="guid-escape-sequences"></a>Escape-последовательности GUID
ODBC использует escape-последовательности для литералов GUID. Синтаксис этой escape-последовательности выглядит следующим образом:  
  
```  
{guid 'nnnnnnnn-nnnn-nnnn-nnnn-nnnnnnnnnnnn'}  
```  
  
## <a name="remarks"></a>Замечания  
 В нотации BNF синтаксис выглядит следующим образом:  
  
 *ODBC-GUID-escape* :: =  
     *ODBC-ESC-идентификатор GUID инициатора* "*GUID-value*" *ODBC-ESC-признак конца*  
  
 *ODBC-ESC-инициатор* :: = {  
  
 *ODBC-ESC-признак конца* :: =}  
  
 *GUID-value* :: = *таймер — минимальное значение GUID-разделитель — часы среднего* значения с разделителями-запятыми-значение GUID-разделитель "часы — последовательность-значение GUID-разделитель"  
  
 *GUID-separator* :: =-  
  
 *Clock-низкое значение* :: = *hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit*  
  
 *Clock-средняя-значение* :: = *hex_digit hex_digit hex_digit hex_digit*  
  
 *часы-высокое значение* :: = *hex_digit hex_digit hex_digit hex_digit*  
  
 *Clock-seq-value* :: = *hex_digit hex_digit hex_digit hex_digit*  
  
 *часы-node-значение* :: = *hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit*  
  
 *hex_digit* :: = 0 &#124; 1 &#124; 2 &#124; 3 &#124; 4 &#124; 5 &#124; 6 &#124; 7 &#124; 8 &#124; 9 &#124; A &#124; B &#124; C &#124; D &#124; E &#124; F  
  
 Escape-последовательность литерала GUID поддерживается, если тип данных GUID поддерживается источником данных. Приложение должно вызвать **SQLGetTypeInfo** , чтобы определить, поддерживается ли этот тип данных.
