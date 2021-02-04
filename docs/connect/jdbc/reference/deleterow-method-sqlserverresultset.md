---
description: Метод deleteRow (SQLServerResultSet)
title: Метод deleteRow (SQLServerResultSet) | Документация Майкрософт
ms.custom: ''
ms.date: 01/20/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerResultSet.deleteRow
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: aa04a644-c7c2-4738-8b6e-7fea566d2c16
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 8c515b4554b29b9db6ae91ba303834820c80aa63
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99163445"
---
# <a name="deleterow-method-sqlserverresultset"></a>Метод deleteRow (SQLServerResultSet)

[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Удаляет текущую строку из этого объекта [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) и из используемой базы данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
public void deleteRow()  
```  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод deleteRow задается с помощью метода deleteRow в интерфейсе java.sql.ResultSet.  
  
 Этот метод не может быть вызван при нахождении курсора в строке вставки.  
  
 Если используются курсоры, управляемые набором ключей, этот метод оставляет пробел в результирующем наборе. Его наличие можно проверить с помощью метода [rowDeleted](../../../connect/jdbc/reference/rowdeleted-method-sqlserverresultset.md). Номера строк в результирующем наборе не изменяются.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Класс SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
