---
description: Escape-последовательности интервалов
title: Escape-последовательности интервалов | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- interval literals [ODBC]
- escape sequences [ODBC], interval
- ODBC escape sequences [ODBC], interval
ms.assetid: 303e8dab-8f13-4fa5-857f-15cc1f75bdd6
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 0badac832ee4cf4e29f148dbd39a7989536b9c29
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99176502"
---
# <a name="interval-escape-sequences"></a>Escape-последовательности интервалов
ODBC использует escape-последовательности для литералов интервала. Синтаксис этой escape-последовательности выглядит следующим образом:  
  
 {*Interval-Literal*}  
  
 Синтаксис BNF *-литерала интервала* см. в разделе [синтаксис литералов интервала](../../../odbc/reference/appendixes/interval-literal-syntax.md) далее в этом приложении.  
  
 Escape-последовательность литерала Interval поддерживается, если типы данных интервала поддерживаются источником данных. Приложение должно вызывать **SQLGetTypeInfo** , чтобы определить, поддерживаются ли эти типы данных.
