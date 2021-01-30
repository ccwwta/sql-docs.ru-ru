---
description: Сопоставление SQLGetConnectOption
title: Сопоставление SQLGetConnectOption | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- mapping deprecated functions [ODBC], SQLGetConnectOption
- SQLGetConnectOption function [ODBC], mapping
ms.assetid: e3792fe4-a955-473a-a297-c1b2403660c4
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: cdc5f2e9249e262d0d3da9a69607861bfe64bc25
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99202802"
---
# <a name="sqlgetconnectoption-mapping"></a>Сопоставление SQLGetConnectOption
Когда приложение вызывает **SQLGetConnectOption** через драйвер ODBC *3. x* , вызов метода  
  
```  
SQLGetConnectOption(hdbc, fOption, pvParam)   
```  
  
 сопоставляется следующим образом:  
  
-   Если *параметром fOption* указывает параметр соединения, определяемый ODBC, который возвращает строку, диспетчер драйверов вызывает метод  
  
    ```  
    SQLGetConnectAttr(ConnectionHandle, Attribute, ValuePtr, BufferLength, NULL)  
    ```  
  
-   Если *параметром fOption* указывает параметр соединения, определяемый ODBC, который возвращает 32-разрядное целое значение, диспетчер драйверов вызывает  
  
    ```  
    SQLGetConnectAttr(ConnectionHandle, Attribute, ValuePtr, 0, NULL)  
    ```  
  
-   Если *параметром fOption* указывает параметр инструкции, определяемый драйвером, диспетчер драйверов вызывает  
  
    ```  
    SQLGetConnectAttr(ConnectionHandle, Attribute, ValuePtr, BufferLength, NULL)  
    ```  
  
 В предыдущих трех случаях аргументу *коннектионхандле* присваивается значение в *хдбк*, аргументу *атрибута* присваивается значение в *параметром fOption*, а аргументу *ValuePtr* присваивается то же значение, что и *пвпарам*.  
  
 Для параметров соединения, определенных ODBC, диспетчер драйверов устанавливает аргумент *BufferLength* в вызове **SQLGetConnectAttr** до предопределенной максимальной длины (SQL_MAX_OPTION_STRING_LENGTH); для параметра соединения, не предназначенного для строки, *BufferLength* имеет значение 0.  
  
 Для драйвера ODBC *3. x* диспетчер драйверов больше не проверяет, находится ли *параметр* между SQL_CONN_OPT_MIN и SQL_CONN_OPT_MAX или больше SQL_CONNECT_OPT_DRVR_START. Драйвер должен проверить допустимость значений параметров.
