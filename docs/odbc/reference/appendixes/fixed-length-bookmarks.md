---
description: Закладки фиксированной длины
title: Fixed-Length закладки | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- backward compatibility [ODBC], bookmarks
- bookmarks [ODBC]
- compatibility [ODBC], bookmarks
- fixed-length bookmarks [ODBC]
ms.assetid: cbd8185e-fb03-408f-b80b-1a2e164534fd
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 2d5eb7acd97a83be0d150cec8b19a5a3e25a7bf6
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99194804"
---
# <a name="fixed-length-bookmarks"></a>Закладки фиксированной длины
Если драйвер ODBC *3. x* должен работать с приложением ODBC *2. x* , использующим закладки фиксированной длины, драйвер должен поддерживать следующее:  
  
-   SQL_UB_ON в качестве значения параметра инструкции SQL_USE_BOOKMARKS. (SQL_UB_ON не рекомендуется использовать в ODBC *3. x*.)  
  
-   Параметр инструкции SQL_GET_BOOKMARK.
