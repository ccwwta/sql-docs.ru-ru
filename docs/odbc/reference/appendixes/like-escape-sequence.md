---
description: Escape-последовательность LIKE
title: КАК escape-последовательность | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- ODBC escape sequences [ODBC], LIKE
- LIKE escape sequence [ODBC]
- escape sequences [ODBC], LIKE
ms.assetid: 798d75ea-be9d-4bef-b297-318bc327f1ca
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: d32b0470cb2adf0960e23dac17d8cb4942f296c0
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99184398"
---
# <a name="like-escape-sequence"></a>Escape-последовательность LIKE
ODBC использует escape-последовательности для предложения LIKE. Синтаксис этой escape-последовательности выглядит следующим образом:  
  
```  
{'escape-character'}  
```  
  
## <a name="remarks"></a>Замечания  
 В нотации BNF синтаксис выглядит следующим образом:  
  
 *ODBC-Like-escape* :: =  
  
 *ODBC-ESC-* Escape-*символ*"управляющая последовательность" *ODBC-ESC-признак конца*  
  
 *escape-символ* :: = *символ*  
  
 *ODBC-ESC-инициатор* :: = {  
  
 *ODBC-ESC-признак конца* :: =}  
  
 Чтобы определить, поддерживает ли драйвер escape-последовательность LIKE, приложение может вызвать **SQLGetInfo** с типом сведений SQL_LIKE_ESCAPE_CLAUSE.
