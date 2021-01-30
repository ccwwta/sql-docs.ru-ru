---
description: Escape-последовательность скалярной функции
title: Escape-последовательность скалярной функции | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- escape sequences [ODBC], scalar function
- scalar functions [ODBC], escape sequences
- ODBC escape sequences [ODBC], scalar function
ms.assetid: aaf5d516-e090-445f-8839-9e39581c69c7
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: f17323281ba666d9657b8c1f7e555b61ef24e19f
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99187120"
---
# <a name="scalar-function-escape-sequence"></a>Escape-последовательность скалярной функции
ODBC использует escape-последовательности для скалярных функций. Синтаксис этой escape-последовательности выглядит следующим образом:  
  
```  
{fn scalar-function}  
```  
  
## <a name="remarks"></a>Замечания  
 В нотации BNF синтаксис выглядит следующим образом:  
  
 *ODBC-скалярная функция-escape* :: =  
  
 *ODBC-ESC-инициатор* , *Скалярная функция ODBC-ESC-признак конца*  
  
 *Скалярная функция* :: = *Function-Name* (*Argument-List*)  
  
 (Определения для нетерминальных *функций-имя* и *имя функции* (*Argument-List*) являются производными от списка скалярных функций в [приложении E: скалярные функции](../../../odbc/reference/appendixes/appendix-e-scalar-functions.md).)  
  
 *ODBC-ESC-инициатор* :: = {  
  
 *ODBC-ESC-признак конца* :: =}  
  
 Чтобы определить, поддерживает ли источник данных процедуры, и драйвер поддерживает синтаксис вызова процедуры ODBC, приложение может вызвать **SQLGetInfo**. Дополнительные сведения см. в разделе [Приложение E. скалярные функции](../../../odbc/reference/appendixes/appendix-e-scalar-functions.md).
