---
description: Сопоставление SQLFreeEnv
title: Сопоставление SQLFreeEnv | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- SQLFreeEnv function [ODBC], mapping
- mapping deprecated functions [ODBC], SQLFreeEnv
ms.assetid: c0f76455-d072-4bae-bee7-452277dfa479
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 99c4976c5516f8259fdb9c48dde5093c4fa686b2
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99202825"
---
# <a name="sqlfreeenv-mapping"></a>Сопоставление SQLFreeEnv
Когда приложение вызывает **SQLFreeEnv** через драйвер ODBC *3. x* , вызов метода  
  
```  
SQLFreeEnv(henv)   
```  
  
 сопоставлен с  
  
```  
SQLFreeHandle(SQL_HANDLE_ENV,Handle)  
```  
  
 с аргументом *Handle* , имеющим значение в *хенв*.
