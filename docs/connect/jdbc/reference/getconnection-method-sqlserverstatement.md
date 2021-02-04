---
description: Метод getConnection (SQLServerStatement)
title: Метод getConnection (SQLServerStatement) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerStatement.getConnection
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 6f341d0b-265a-415e-abe5-8f408fedbb21
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: c721e722efde635cc81aefb6fbb03101845befe2
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99163277"
---
# <a name="getconnection-method-sqlserverstatement"></a>Метод getConnection (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает объект [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md), создавший данный объект [SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public final java.sql.Connection getConnection()  
```  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getConnection задается с помощью метода getConnection в интерфейсе java.sql.Statement.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [Класс SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
