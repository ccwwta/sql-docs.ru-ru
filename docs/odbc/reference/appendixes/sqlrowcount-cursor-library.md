---
description: SQLRowCount (библиотека курсоров)
title: SQLRowCount (библиотека курсоров) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- SQLRowCount function [ODBC], Cursor Library
ms.assetid: 781cf5a5-325e-4523-8633-d96d9e98277c
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 9a8efc6fdef2a3bef563a5289acdef55958a03be
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99202674"
---
# <a name="sqlrowcount-cursor-library"></a>SQLRowCount (библиотека курсоров)
> [!IMPORTANT]  
>  Эта функция будет удалена в следующей версии Windows. Избегайте использования этой функции в новых разработках и запланируйте изменение приложений, которые в настоящее время используют эту функцию. Корпорация Майкрософт рекомендует использовать функцию курсора драйвера.  
  
 В этом разделе обсуждается использование функции **SQLRowCount** в библиотеке курсоров. Общие сведения о **SQLRowCount** см. в разделе [функция SQLRowCount](../../../odbc/reference/syntax/sqlrowcount-function.md).  
  
 Когда приложение вызывает **SQLRowCount** с инструкцией, связанной с курсором, Библиотека курсоров возвращает число строк данных, извлеченных из драйвера.  
  
 Когда приложение вызывает **SQLRowCount** с инструкцией, связанной с позиционированным обновлением или инструкцией DELETE, Библиотека курсоров возвращает число строк, затронутых инструкцией.  
  
 Когда приложение вызывает **SQLRowCount** после инструкции **SELECT** , Библиотека курсоров возвращает значение-1.
