---
description: SQLFreeStmt (библиотека курсоров)
title: SQLFreeStmt (библиотека курсоров) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- SQLFreeStmt function [ODBC], Cursor Library
ms.assetid: 47bfbd4d-9453-4609-958d-1e05794cb223
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 3b7ebdcfc5a9997efb4301852b1aae3c1408464d
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99202822"
---
# <a name="sqlfreestmt-cursor-library"></a>SQLFreeStmt (библиотека курсоров)
> [!IMPORTANT]  
>  Эта функция будет удалена в следующей версии Windows. Избегайте использования этой функции в новых разработках и запланируйте изменение приложений, которые в настоящее время используют эту функцию. Корпорация Майкрософт рекомендует использовать функцию курсора драйвера.  
  
 В этом разделе обсуждается использование функции **SQLFreeStmt** в библиотеке курсоров. Общие сведения о **SQLFreeStmt** см. в разделе [Функция SQLFreeStmt](../../../odbc/reference/syntax/sqlfreestmt-function.md).  
  
 Если приложение вызывает **SQLFreeStmt** с параметром SQL_UNBIND после вызова **SQLExtendedFetch**, **SQLFetch** или **SQLFetchScroll**, Библиотека курсоров возвращает ошибку. Прежде чем можно будет отменить привязку столбцов результирующего набора, приложение должно вызвать **SQLCloseCursor** или **SQLFreeStmt** с параметром SQL_CLOSE.
