---
description: Кэш библиотеки курсоров
title: Кэш библиотеки курсоров | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- ODBC cursor library [ODBC], cache
- cursor library [ODBC], cache
- cache [ODBC]
ms.assetid: d6a91cd6-3905-4e3a-98ab-37fce893dbe1
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 0de0f04795cd2e0ad8f007155cad2b9329c3d082
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99165369"
---
# <a name="cursor-library-cache"></a>Кэш библиотеки курсоров
> [!IMPORTANT]  
>  Эта функция будет удалена в следующей версии Windows. Избегайте использования этой функции в новых разработках и запланируйте изменение приложений, которые в настоящее время используют эту функцию. Корпорация Майкрософт рекомендует использовать функцию курсора драйвера.  
  
 Для каждой строки данных в результирующем наборе библиотека курсоров кэширует данные для каждого привязанного столбца, длину данных в каждом связанном столбце и состояние строки. Библиотека курсоров использует значения в кэше для возврата через **SQLFetch** и **SQLFetchScroll** и для создания поисковых инструкций для позиционированных операций. Дополнительные сведения см. в разделе [Построение поисковых инструкций](../../../odbc/reference/appendixes/constructing-searched-statements.md).  
  
 Этот раздел содержит следующие подразделы.  
  
-   [Столбец данных](../../../odbc/reference/appendixes/column-data.md)  
  
-   [Длина данных столбца](../../../odbc/reference/appendixes/length-of-column-data.md)  
  
-   [Статус строки](../../../odbc/reference/appendixes/row-status.md)  
  
-   [Расположение кэша](../../../odbc/reference/appendixes/location-of-cache.md)
