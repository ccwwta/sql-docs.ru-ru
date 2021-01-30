---
description: SQL_C_TCHAR
title: SQL_C_TCHAR | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- sql_c_tchar [ODBC]
- pseudo-type identifiers [ODBC], SQL_C_TCHAR
- data types [ODBC], pseudo-type identifiers
ms.assetid: 9e27c8bd-ee15-4ce9-b70a-34cf1bf16f4c
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: a399570a15f04d8ace61664a445c5283d629bf6a
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99193052"
---
# <a name="sql_c_tchar"></a>SQL_C_TCHAR
Идентификатор типа SQL_C_TCHAR на самом деле не определяет тип данных; Это макрос, который существует в файле заголовка для преобразования в Юникод. Он заменяется SQL_C_CHAR или SQL_C_WCHAR в зависимости от значения **#define** Юникода. Это полезно для приложения, которое передает символьные данные, компилируемые как приложения ANSI и Юникод.
