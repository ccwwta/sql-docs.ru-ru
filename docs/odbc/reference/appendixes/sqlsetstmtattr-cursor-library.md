---
description: SQLSetStmtAttr (библиотека курсоров)
title: SQLSetStmtAttr (библиотека курсоров) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- SQLSetStmtAttr function [ODBC], Cursor Library
ms.assetid: 6018a733-c2c8-4047-92ec-92cf85031767
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 8a395052df9eb5623e63463e3e79722769583721
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99202590"
---
# <a name="sqlsetstmtattr-cursor-library"></a>SQLSetStmtAttr (библиотека курсоров)
> [!IMPORTANT]  
>  Эта функция будет удалена в следующей версии Windows. Избегайте использования этой функции в новых разработках и запланируйте изменение приложений, которые в настоящее время используют эту функцию. Корпорация Майкрософт рекомендует использовать функцию курсора драйвера.  
  
 В этом разделе обсуждается использование функции **SQLSetStmtAttr** в библиотеке курсоров. Общие сведения о **SQLSetStmtAttr** см. в разделе [функция SQLSetStmtAttr](../../../odbc/reference/syntax/sqlsetstmtattr-function.md).  
  
 Библиотека курсоров поддерживает следующие атрибуты инструкции с **SQLSetStmtAttr**:  

:::row:::
    :::column:::
        SQL_ATTR_CONCURRENCY  
        SQL_ATTR_CURSOR_TYPE  
        SQL_ATTR_FETCH_BOOKMARK_PTR  
        SQL_ATTR_PARAM_BIND_OFFSET_PTR  
        SQL_ATTR_PARAM_BIND_TYPE  
    :::column-end:::
    :::column:::
        SQL_ATTR_ROW_BIND_OFFSET_PTR  
        SQL_ATTR_ROW_BIND_TYPE  
        SQL_ATTR_ROWSET_ARRAY_SIZE  
        SQL_ATTR_SIMULATE_CURSOR  
        SQL_ATTR_USE_BOOKMARKS  
    :::column-end:::
:::row-end:::

 Библиотека курсоров поддерживает только значения SQL_CURSOR_FORWARD_ONLY и SQL_CURSOR_STATIC атрибута инструкции SQL_ATTR_CURSOR_TYPE.  
  
 Для однонаправленных курсоров библиотека курсоров поддерживает SQL_CONCUR_READ_ONLY значение атрибута инструкции SQL_ATTR_CONCURRENCY. Для статических курсоров библиотека курсоров поддерживает SQL_CONCUR_READ_ONLY и SQL_CONCUR_VALUES значения атрибута SQL_ATTR_CONCURRENCY инструкции.  
  
 Библиотека курсоров поддерживает только SQL_SC_NON_UNIQUE значение атрибута инструкции SQL_ATTR_SIMULATE_CURSOR.  
  
 Хотя Спецификация ODBC поддерживает вызовы **SQLSetStmtAttr** с атрибутами SQL_ATTR_PARAM_BIND_TYPE или SQL_ATTR_ROW_BIND_TYPE после вызова **SQLFetch** или **SQLFetchScroll** , Библиотека курсоров не имеет. Прежде чем он сможет изменить тип привязки в библиотеке курсоров, приложение должно закрыть курсор. Библиотека курсоров поддерживает изменение атрибутов SQL_ATTR_ROW_BIND_OFFSET_PTR, SQL_ATTR_PARAM_BIND_OFFSET_PTR, SQL_ATTR_ROWS_FETCHED_PTR и SQL_ATTR_PARAMS_PROCESSED_PTR, когда курсор открыт.  
  
 Приложение может вызвать **SQLSetStmtAttr** с **атрибутом** SQL_ATTR_ROW_ARRAY_SIZE, чтобы изменить размер набора строк, пока курсор открыт. Новый размер набора строк вступит в силу при следующем вызове **SQLFetchScroll** или **SQLFetch** .  
  
 Библиотека курсоров поддерживает задание SQL_ATTR_PARAM_BIND_OFFSET_PTR или SQL_ATTR_ROW_BIND_OFFSET_PTR атрибута инструкции для включения смещений привязок. Смещение привязки не будет использоваться для вызовов **SQLFetch** , если библиотека курсоров используется с ODBC 2. драйвер *x* .  
  
 Библиотека курсоров поддерживает задание для атрибута SQL_ATTR_USE_BOOKMARKS инструкции значения SQL_UB_VARIABLE.
