---
description: Метод getResultSetType (SQLServerStatement)
title: Метод getResultSetType (SQLServerStatement) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerStatement.getResultSetType
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 260da35f-ddf6-4111-8519-69956ea3072e
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 38d4f8d36925d93550780dbf6df7923529b0c9d3
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99162393"
---
# <a name="getresultsettype-method-sqlserverstatement"></a>Метод getResultSetType (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает тип результирующего набора для объектов [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md), созданных этим объектом [SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public final int getResultSetType()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение **int**, указывающее тип результирующего набора.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getResultSetType задается с помощью метода getResultSetType в интерфейсе java.sql.Statement.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [Класс SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
