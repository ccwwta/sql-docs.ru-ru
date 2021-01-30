---
description: Сопоставление SQLAllocStmt
title: Сопоставление SQLAllocStmt | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- mapping deprecated functions [ODBC], SQLAllocStmt
- SQLAllocStmt function [ODBC], mapping
ms.assetid: a2449dbb-1b6c-4b49-81b9-ebdddd4442fd
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: aa2b3392ce9cce9b6cf98d18fe6672bb0034bf2a
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99202962"
---
# <a name="sqlallocstmt-mapping"></a>Сопоставление SQLAllocStmt
Когда приложение вызывает **SQLAllocStmt** через драйвер ODBC *3. x* , вызов:  
  
```  
SQLAllocStmt(hdbc, phstmt)  
```  
  
 сопоставляется с **функцию SQLAllocHandle** диспетчером драйверов в драйвере следующим образом:  
  
```  
SQLAllocHandle(SQL_HANDLE_STMT, InputHandle, OutputHandlePtr)  
```  
  
 Если для *инпусандле* задано значение *хдбк* , а для *аутпусандлептр* задано значение *фстмт*.
