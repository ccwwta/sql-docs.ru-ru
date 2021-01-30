---
description: Синтаксис числовых литералов
title: Синтаксис числового литерала | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- ODBC literals [ODBC], numeric
- numeric literals [ODBC]
- literals [ODBC], numeric
ms.assetid: fb17498d-4f1d-4b3d-b33d-1e62c7d3c32d
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 541f2fa53d6aeb9a387117b17f0917cb110dc630
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99193299"
---
# <a name="numeric-literal-syntax"></a>Синтаксис числовых литералов
Для числовых литералов в ODBC используется следующий синтаксис:  
  
 *числовой литерал* :: =- *numeric-Literal &#124; без знака-числового литерала*  
  
 *знак-numeric-Literal* :: = [*знак*] *без знака — числовой литерал*  
  
 *неподписанный-numeric-Literal* :: = *СОВПАД-numeric-Literal &#124; приблизительный числовой литерал*  
  
 *СОВПАД-numeric-Literal* :: = *без знака-целое число* [*точка*[*без знака-целое*]] *&#124;периода без знака — целое число*  
  
 *знак* :: = *плюс-знак &#124; минус-знак*  
  
 Примерное значение экспоненты " *приблизительный-числовой литерал* :: = *мантисса E* "  
  
 *мантисса* :: = *СОВПАД-numeric-Literal*  
  
 *экспонента* :: = *целое число со знаком*  
  
 *знак-целое* :: = [*знак*] без *знака — целое число*  
  
 *без знака — целое число* :: = *цифра...*  
  
 *плюс-знак* :: = *+*  
  
 *минус-Sign* :: =-  
  
 *digit* :: = 1 &#124; 2 &#124; 3 &#124; 4 &#124; 5 &#124; 6 &#124; 7 &#124; 8 &#124; 9 &#124; 0  
  
 *period* :: =.
