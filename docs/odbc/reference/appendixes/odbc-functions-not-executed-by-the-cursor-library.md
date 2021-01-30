---
description: Функции ODBC, не выполняемые библиотекой курсоров
title: Функции ODBC, не выполняемые библиотекой курсоров | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- cursor library [ODBC], functions
- functions [ODBC], cursor library
- ODBC functions [ODBC], cursor library
- ODBC cursor library [ODBC], functions
ms.assetid: f2941522-75eb-4db9-9468-4800b884dac2
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: e1e9dc26730d9bdc5b10ba9f4c35c46f6500f6bc
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99160864"
---
# <a name="odbc-functions-not-executed-by-the-cursor-library"></a>Функции ODBC, не выполняемые библиотекой курсоров
> [!IMPORTANT]  
>  Эта функция будет удалена в следующей версии Windows. Избегайте использования этой функции в новых разработках и запланируйте изменение приложений, которые в настоящее время используют эту функцию. Корпорация Майкрософт рекомендует использовать функцию курсора драйвера.  
  
 Библиотека курсоров не выполняет следующие функции. Когда приложение вызывает одну из этих функций, диспетчер драйверов вызывает драйвер, а не библиотеку курсоров.  
  
|||  
|-|-|  
|**SQLFetch**|**SQLGetEnvAttr**|  
|**SQLGetConnectAttr**|**SQLSetDescRec**|  
|**SQLGetDiagField**|**SQLSetEnvAttr**|  
|**Функции SQLGetDiagRec**||
