---
description: Статус строки
title: Состояние строки | Документация Майкрософт
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
- row status [ODBC]
- cache [ODBC]
ms.assetid: 0f0b1fb6-f697-4ced-811c-2908e210bc71
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 491e0b420e31f1fe8e66c73f9ab8d89cb1e7e1cd
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99187150"
---
# <a name="row-status"></a>Статус строки
> [!IMPORTANT]  
>  Эта функция будет удалена в следующей версии Windows. Избегайте использования этой функции в новых разработках и запланируйте изменение приложений, которые в настоящее время используют эту функцию. Корпорация Майкрософт рекомендует использовать функцию курсора драйвера.  
  
 Библиотека курсоров создает буфер в кэше для состояния строки. Библиотека курсоров извлекает значения для массива состояния строки (указанного в атрибуте оператора SQL_ATTR_ROW_STATUS_PTR) из этого буфера. Для каждой строки библиотека курсоров задает для этого буфера следующие сведения:  
  
-   SQL_ROW_DELETED при выполнении инструкции позиционированного удаления в строке.  
  
-   SQL_ROW_ERROR при возникновении ошибки при получении строки из источника данных с помощью **SQLFetch**.  
  
-   SQL_ROW_SUCCESS, когда она успешно извлекает строку из источника данных с помощью **SQLFetch**.  
  
-   SQL_ROW_UPDATED при выполнении инструкции позиционированного обновления в строке.
