---
description: Метод getColumnClassName (SQLServerResultSetMetaData)
title: Метод getColumnClassName (SQLServerResultSetMetaData) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerResultSetMetaData.getColumnClassName
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 2c118790-5dd2-4b10-93b6-7f065ee324ce
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 179840b10345ba917871d6b6b73503650ced89c9
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99168013"
---
# <a name="getcolumnclassname-method-sqlserverresultsetmetadata"></a>Метод getColumnClassName (SQLServerResultSetMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает полное имя Java-класса, экземпляры которого создаются при вызове метода [getObject](../../../connect/jdbc/reference/getobject-method-sqlserverresultset.md) класса [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) для получения значения столбца.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public java.lang.String getColumnClassName(int column)  
```  
  
#### <a name="parameters"></a>Параметры  
 *column*  
  
 Значение типа **int**, указывающее индекс столбца.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение типа **String**, содержащее полное имя класса.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getColumnClassName указывается с помощью метода getColumnClassName в интерфейсе java.sql.ResultSetMetaData.  
  
## <a name="see-also"></a>См. также:  
 [Методы SQLServerResultSetMetaData](../../../connect/jdbc/reference/sqlserverresultsetmetadata-methods.md)   
 [Элементы SQLServerResultSetMetaData](../../../connect/jdbc/reference/sqlserverresultsetmetadata-members.md)   
 [Класс SQLServerResultSetMetaData](../../../connect/jdbc/reference/sqlserverresultsetmetadata-class.md)  
  
  
