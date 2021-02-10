---
description: Указание свойств подключения
title: Задание свойств соединения | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- connection properties [ADO]
- connections [ADO]
ms.assetid: 49456201-b085-4851-9686-e814136b07be
author: rothja
ms.author: jroth
ms.openlocfilehash: d69af7af414c1c864d47e39160f4b4a94d726ac9
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100032456"
---
# <a name="specifying-connection-properties"></a>Указание свойств подключения
Можно указать большую часть сведений, указанных в [строке подключения](../../../ado/guide/data/creating-a-connection-string.md) , задав свойства объекта **соединения** перед открытием соединения. Например, можно добиться того же результата, что и в строке подключения, описанной в разделе [Создание строки подключения](../../../ado/guide/data/creating-a-connection-string.md) с помощью следующего кода.  
  
```  
With objConn  
.Provider = "SQLOLEDB"  
.Properties("Data Source") = "MySqlServer"  
   .Properties("Integrated Security") = "SSPI"  
.Open  
.DefaultDatabase = "Northwind"  
End With  
```  
  
 DefaultDatabase задается только после открытия подключения.  
  
> [!NOTE]
>  В ADO не следует использовать пароль, содержащий точку с запятой (";"), если пароль не заключен в одинарные кавычки.
