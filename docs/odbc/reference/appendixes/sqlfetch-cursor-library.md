---
description: SQLFetch (библиотека курсоров)
title: SQLFetch (библиотека курсоров) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- SQLFetch function [ODBC], Cursor Library
ms.assetid: 35a0d493-778b-4fb1-84ee-a13540e2fe0e
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 7e0ed0b94d4ad66c22ef1a29055c7a0144e4f941
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99202856"
---
# <a name="sqlfetch-cursor-library"></a>SQLFetch (библиотека курсоров)
> [!IMPORTANT]  
>  Эта функция будет удалена в следующей версии Windows. Избегайте использования этой функции в новых разработках и запланируйте изменение приложений, которые в настоящее время используют эту функцию. Корпорация Майкрософт рекомендует использовать функцию курсора драйвера.  
  
 В этом разделе обсуждается использование функции **SQLFetch** в библиотеке курсоров. Общие сведения о **SQLFetch** см. в разделе [функция SQLFetch](../../../odbc/reference/syntax/sqlfetch-function.md).  
  
 При использовании библиотеки курсоров вызовы **SQLFetch** не могут смешиваться с вызовами либо **SQLFetchScroll** , либо **SQLExtendedFetch**.  
  
 Если при вызове **SQLFetch** с параметром SQL_ATTR_ROW_ARRAY_SIZE задано значение больше 1, то библиотека курсоров передаст вызов драйвера. Если драйвер является ODBC 2. драйвер *x* , размер набора строк будет проигнорирован, а вызов **SQLFetch** будет возвращать одну строку данных.  
  
 Если библиотека курсоров используется с ODBC 2. драйвер *x* , смещение привязки (как определено атрибутом SQL_ATTR_ROW_BIND_OFFSET_PTR оператора) не используется при вызове **SQLFetch** .  
  
 При загрузке библиотеки курсоров приложение не может вызвать **SQLFetch** для выборки столбцов закладки. Библиотека курсоров передает вызов **SQLFetch** через драйвер, но вызов функции для включения закладок и привязки столбца закладка перехватывается библиотекой курсоров.
