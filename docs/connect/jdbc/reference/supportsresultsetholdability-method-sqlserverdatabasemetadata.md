---
description: Метод supportsResultSetHoldability (SQLServerDatabaseMetaData)
title: Метод supportsResultSetHoldability (SQLServerDatabaseMetaData) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerDatabaseMetaData.supportsResultSetHoldability
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: ab575792-fd11-4ff3-8847-1368e7a322c5
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 429848642c35b5e872faa0568b500e975dfc3975
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99158244"
---
# <a name="supportsresultsetholdability-method-sqlserverdatabasemetadata"></a>Метод supportsResultSetHoldability (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает значение, определяющее, поддерживает ли эта база данных заданную возможность сохранения результирующих наборов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public boolean supportsResultSetHoldability(int holdability)  
```  
  
#### <a name="parameters"></a>Параметры  
 *holdability*  
  
 Значение **int**, указывающее возможность ожидания результирующего набора. Возможны следующие значения:  
  
 ResultSet.HOLD_CURSORS_OVER_COMMIT  
  
 ResultSet.CLOSE_CURSORS_AT_COMMIT  
  
## <a name="return-value"></a>Возвращаемое значение  
 **true**, если поддерживается. В противном случае — **false**.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод supportsResultSetHoldability указывается с помощью метода supportsResultSetHoldability в интерфейсе java.sql.DatabaseMetaData.  
  
## <a name="see-also"></a>См. также:  
 [Методы SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [Элементы SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [Класс SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
