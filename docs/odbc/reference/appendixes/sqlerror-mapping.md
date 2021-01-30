---
description: Сопоставление SQLError
title: Сопоставление SQLError | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- mapping deprecated functions [ODBC], SQLError
- SQLError function [ODBC], mapping
ms.assetid: 802ac711-7e5d-4152-9698-db0cafcf6047
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 95cb5d4c22ff0baec48e20da2be582d0fbab97c6
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99202882"
---
# <a name="sqlerror-mapping"></a>Сопоставление SQLError
Когда приложение вызывает **SqlError** через драйвер ODBC *3. x* , вызов метода  
  
```  
SQLError(henv, hdbc, hstmt, szSqlState, pfNativeError, szErrorMsg, cbErrorMsgMax, pcbErrorMsg)   
```  
  
 сопоставлен с  
  
```  
SQLGetDiagRec(HandleType, Handle, RecNumber, szSqlstate, pfNativeErrorPtr, szErrorMsg, cbErrorMsgMax, pcbErrorMsg)  
```  
  
 Если для аргумента *параметром handletype* задано значение SQL_HANDLE_ENV, SQL_HANDLE_DBC или SQL_HANDLE_STMT, соответственно, и аргумент *Handle* имеет значение в *хенв*, *хдбк* или *хстмт*, в зависимости от ситуации. Аргумент *рекнумбер* определяется диспетчером драйверов.
