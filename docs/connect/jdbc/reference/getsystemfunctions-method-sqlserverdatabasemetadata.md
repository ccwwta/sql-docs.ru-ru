---
description: Метод getSystemFunctions (SQLServerDatabaseMetaData)
title: Метод getSystemFunctions (SQLServerDatabaseMetaData) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerDatabaseMetaData.getSystemFunctions
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 6d390ec5-9ee2-49c4-b661-a93b55691dd1
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 0cdb3113a554e1a0a69b37f45c8959245b8b70a9
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99162145"
---
# <a name="getsystemfunctions-method-sqlserverdatabasemetadata"></a>Метод getSystemFunctions (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает список с разделителями-запятыми системных функций, доступных в этой базе данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public java.lang.String getSystemFunctions()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение **String**, содержащее список системных функций.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getSystemFunctions определен с помощью метода getSystemFunctions в интерфейсе java.sql.DatabaseMetaData.  
  
## <a name="see-also"></a>См. также:  
 [Методы SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [Элементы SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [Класс SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
