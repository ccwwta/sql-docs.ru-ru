---
description: Метод getMetaData (SQLServerResultSet)
title: Метод getMetaData (SQLServerResultSet) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerResultSet.getMetaData
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 9dcdbf69-1d47-422c-842e-0bed5afdcb93
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: c762a21d9bf1d478e7c273224f54bd912519b87f
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99175474"
---
# <a name="getmetadata-method-sqlserverresultset"></a>Метод getMetaData (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Извлекает количество, типы и свойства столбцов для этого объекта [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public java.sql.ResultSetMetaData getMetaData()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект [SQLServerResultSetMetaData](../../../connect/jdbc/reference/sqlserverresultsetmetadata-class.md).  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getMetaData задается с помощью метода getMetaData в интерфейсе java.sql.ResultSet.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Класс SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
