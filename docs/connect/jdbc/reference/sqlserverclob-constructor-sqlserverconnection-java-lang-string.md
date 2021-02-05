---
description: Конструктор SQLServerClob (SQLServerConnection, java.lang.String)
title: Конструктор SQLServerClob (SQLServerConnection, java.lang.String) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerConnection.SQLServerClob (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 7058f4f7-ef3e-4d62-90d1-79299708b1eb
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 1b682ecf3dfc85415d8ca505be95fc65856bb465
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99178372"
---
# <a name="sqlserverclob-constructor-sqlserverconnection-javalangstring"></a>Конструктор SQLServerClob (SQLServerConnection, java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Инициализирует новый экземпляр класса [SQLServerClob](../../../connect/jdbc/reference/sqlserverclob-class.md) по заданному объекту [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) и строке данных.  
  
> [!NOTE]  
>  Этот метод устарел в версии драйвера JDBC 2.0. Вместо этого используйте метод [createClob](../../../connect/jdbc/reference/createclob-method-sqlserverconnection.md) класса [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public SQLServerClob(SQLServerConnection connection,  
                     java.lang.String data)  
```  
  
#### <a name="parameters"></a>Параметры  
 *connection*;  
  
 Объект SQLServerConnection.  
  
 *data*  
  
 Данные CLOB.  
  
## <a name="see-also"></a>См. также:  
 [Конструкторы SQLServerClob](../../../connect/jdbc/reference/sqlserverclob-constructors.md)   
 [Элементы SQLServerClob](../../../connect/jdbc/reference/sqlserverclob-members.md)   
 [Класс SQLServerClob](../../../connect/jdbc/reference/sqlserverclob-class.md)  
  
  
