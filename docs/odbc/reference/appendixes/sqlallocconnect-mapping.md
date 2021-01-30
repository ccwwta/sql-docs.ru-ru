---
description: Сопоставление SQLAllocConnect
title: Сопоставление SQLAllocConnect | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- SQLAllocConnect function [ODBC], mapping
- mapping deprecated functions [ODBC], SQLAllocConnect
ms.assetid: ac89dd1f-c565-47cc-8fa3-6fa5f80b5d63
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 3fd1659e4faaee713a2b9d942deb53fe00ea367c
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99202980"
---
# <a name="sqlallocconnect-mapping"></a>Сопоставление SQLAllocConnect
Когда приложение вызывает **SQLAllocConnect** через ODBC 3. драйвер *x* , вызов **SQLAllocConnect**(*хенв*, *фдбк*) сопоставляется с **функцию SQLAllocHandle** следующим образом:  
  
1.  Диспетчер драйверов выделяет соединение и возвращает его приложению.  
  
2.  Когда приложение устанавливает соединение, диспетчер драйверов вызывает метод  
  
    ```  
    SQLAllocHandle(SQL_HANDLE_DBC, InputHandle, OutputHandlePtr)  
    ```  
  
     в драйвере с параметром *инпусандле* установлено значение *хенв*, а для *аутпусандлептр* — значение *фдбк*.
