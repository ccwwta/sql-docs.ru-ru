---
description: Сопоставление SQLTransact
title: Сопоставление SQLTransact | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- mapping deprecated functions [ODBC], SQLTransact
- SQLTransact function [ODBC], mapping
ms.assetid: 8a01041f-3572-46f9-8213-b817f3cf929c
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 09dbfe0c97de5b7b2800869dbb02c1290fd3df3a
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99202567"
---
# <a name="sqltransact-mapping"></a>Сопоставление SQLTransact
Теперь **SQLTransact** заменяется на **SQLEndTran**. Основное различие между двумя функциями заключается в том, что **SQLEndTran** содержит аргумент *параметром handletype*, указывающий область действия, которое необходимо выполнить. Аргумент *параметром handletype* может указывать среду или маркер соединения. Следующий вызов **SQLTransact**:  
  
```  
SQLTransact(henv, hdbc, fType)  
```  
  
 сопоставлен с  
  
```  
SQLEndTran(SQL_HANDLE_DBC, ConnectionHandle, CompletionType);  
```  
  
 Если *коннектионхандле* не равно SQL_NULL_HDBC. Аргументу *коннектионхандле* присваивается значение *хдбк*.  
  
 **SQL_Transact** сопоставлено с  
  
```  
SQLEndTran (SQL_HANDLE_ENV, EnvironmentHandle, CompletionType);  
```  
  
 Если *коннектионхандле* равно SQL_NULL_HDBC. Аргументу *енвиронменсандле* присваивается значение *хенв*.  
  
 В обоих приведенных выше случаях аргументу *комплетионтипе* присваивается то же значение, что и для *fType*.
