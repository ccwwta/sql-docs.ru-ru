---
description: Метод getJDBCMinorVersion (SQLServerDatabaseMetaData)
title: Метод getJDBCMinorVersion (SQLServerDatabaseMetaData) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerDatabaseMetaData.getJDBCMinorVersion
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: d9e153b5-51b7-4e44-b342-f147f04dbe19
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 9e55ded9bf11c6b2a8844000cc2319e2d342e90f
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99162904"
---
# <a name="getjdbcminorversion-method-sqlserverdatabasemetadata"></a>Метод getJDBCMinorVersion (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает дополнительный номер версии JDBC для этого драйвера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public int getJDBCMinorVersion()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение **int**, которое указывает дополнительный номер версии JDBC.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getJDBCMinorVersion задается с помощью метода getJDBCMinorVersion в интерфейсе java.sql.DatabaseMetaData.  
  
## <a name="see-also"></a>См. также:  
 [Методы SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [Элементы SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [Класс SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
