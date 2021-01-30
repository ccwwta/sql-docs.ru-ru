---
description: Escape-последовательность внешнего соединения
title: Escape-последовательность внешнего объединения | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- outer join escape sequence [ODBC]
- escape sequences [ODBC], outer join
- ODBC escape sequences [ODBC], outer join
ms.assetid: 2cfd1525-6677-4d36-9b9e-730496853750
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: e25cde1a4da326d06efe23bc2f7c642e61589ff3
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99160860"
---
# <a name="outer-join-escape-sequence"></a>Escape-последовательность внешнего соединения
ODBC использует escape-последовательности для внешних соединений. Синтаксис этой escape-последовательности выглядит следующим образом:  
  
```  
{oj outer-join}  
```  
  
## <a name="remarks"></a>Замечания  
 В нотации BNF синтаксис выглядит следующим образом:  
  
 *ODBC-OUTER-JOIN — escape* :: =  
  
 *ODBC-ESC-инициатор* ОЖ *внешнее соединение ODBC-ESC-признак конца*  
  
 *внешнее соединение* :: = *Table-name* [*корреляционный имя*] {Left &#124; право &#124; полное}  
  
 ВНЕШНее соединение {имя *таблицы* [*корреляционное* имя] &#124; *внешнее соединение*} включено  
  
 *осуществлять*  
  
 *выполняет*  
  
 *Correlation-Name* :: = *пользовательское имя*  
  
 *ODBC-ESC-инициатор* :: = {  
  
 *ODBC-ESC-признак конца* :: =}  
  
 Чтобы определить, какие части этой инструкции поддерживаются, приложение вызывает **SQLGetInfo** с типом сведений SQL_OJ_CAPABILITIES. Для внешних соединений *условие поиска* должно содержать только условие объединения между указанными *именами таблиц*.
