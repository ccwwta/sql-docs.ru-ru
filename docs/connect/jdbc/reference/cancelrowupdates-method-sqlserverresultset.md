---
description: Метод cancelRowUpdates (SQLServerResultSet)
title: Метод cancelRowUpdates (SQLServerResultSet) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerResultSet.cancelRowUpdates
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 2ecacca4-f7bc-4f5d-886a-da7747fdccae
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 2d5629e6ea7cb25331cbdeedd1440826c3687caf
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99168659"
---
# <a name="cancelrowupdates-method-sqlserverresultset"></a>Метод cancelRowUpdates (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Отменяет обновления текущей строки в этом объекте [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public void cancelRowUpdates()  
```  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод cancelRowUpdates задается с помощью метода cancelRowUpdates в интерфейсе java.sql.ResultSet.  
  
 Этот метод можно вызывать после вызова метода адаптера и перед вызовом метода [updateRow](../../../connect/jdbc/reference/updaterow-method-sqlserverresultset.md) для отката обновлений, выполненных в строке. Если обновления не выполнены или уже вызван метод updateRow, то этот метод не выполняет никаких действий.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Класс SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
