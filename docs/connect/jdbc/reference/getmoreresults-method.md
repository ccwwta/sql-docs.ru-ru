---
description: Метод getMoreResults ()
title: Метод getMoreResults () | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerStatement.getMoreResults ()
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: df89db50-0b2f-4094-820a-30be25ad72fe
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: b4afb4fa108c714eaa4f2b48a1403774b30b5546
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99162719"
---
# <a name="getmoreresults-method-"></a>Метод getMoreResults ()
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Переходит к следующему результату этого объекта [SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public final boolean getMoreResults()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если возвращенный результат — это результирующий набор. В противном случае — **false**.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getMoreResults задается с помощью метода getMoreResults в интерфейсе java.sql.Statement.  
  
 При вызове метода getMoreResults неявно закрываются все открытые объекты результирующего набора, полученные с помощью метода [getResultSet](../../../connect/jdbc/reference/getresultset-method-sqlserverstatement.md).  
  
## <a name="see-also"></a>См. также:  
 [Метод getMoreResults (SQLServerStatement)](../../../connect/jdbc/reference/getmoreresults-method-sqlserverstatement.md)   
 [Элементы SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [Класс SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
