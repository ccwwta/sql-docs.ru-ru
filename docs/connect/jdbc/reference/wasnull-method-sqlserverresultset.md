---
description: Метод wasNull (SQLServerResultSet)
title: Метод wasNull (SQLServerResultSet) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerResultSet.wasNull
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: d37f80ef-d72c-4429-ada3-1d685bdab6d7
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 9270c7c4ab62d2d495a7416c22f59b2d0b69870c
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99181118"
---
# <a name="wasnull-method-sqlserverresultset"></a>Метод wasNull (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Проверяет, является ли последнее считанное значение Null.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public boolean wasNull()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если последнее считанное значение равно null. В противном случае — **false**.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Метод wasNull определен с помощью метода wasNull в интерфейсе java.sql.ResultSet.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Класс SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
