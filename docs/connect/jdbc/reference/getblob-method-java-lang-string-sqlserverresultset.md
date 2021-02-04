---
description: Метод getBlob (java.lang.String) (SQLServerResultSet)
title: Метод getBlob (java.lang.String) (SQLServerResultSet) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerResultSet.getBlob (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 9f730d45-b54a-4961-950e-f4447f7225e1
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 453c130eff80b19953a01abe4d5b92ae3c4ec0cf
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99165668"
---
# <a name="getblob-method-javalangstring-sqlserverresultset"></a>Метод getBlob (java.lang.String) (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Извлекает значение заданного имени столбца в текущей строке этого объекта [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) в виде BLOB-объекта на языке программирования Java.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public java.sql.Blob getBlob(java.lang.String colName)  
```  
  
#### <a name="parameters"></a>Параметры  
 *colName*  
  
 Значение типа **String**, содержащее имя столбца.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект Blob.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getBlob определен с помощью метода getBlob в интерфейсе java.sql.ResultSet.  
  
## <a name="see-also"></a>См. также:  
 [Метод getBlob (SQLServerResultSet)](../../../connect/jdbc/reference/getblob-method-sqlserverresultset.md)   
 [Элементы SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Класс SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
