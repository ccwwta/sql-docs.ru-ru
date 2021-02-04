---
description: Метод getSQLXML (java.lang.String)
title: Метод getSQLXML (java.lang.String) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: f56b192a-3255-4215-b552-8e494fbca083
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 8e7122dadcee3435f9c937ca631244ba60037ce0
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99162254"
---
# <a name="getsqlxml-method-javalangstring"></a>Метод getSQLXML (java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает значение указанного параметра в виде объекта SQLXML по имени параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public final java.sql.SQLXML getSQLXML(java.lang.String parameterName)  
```  
  
#### <a name="parameters"></a>Параметры  
 *parameterName*  
  
 Значение **String**, которое указывает имя параметра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект SQLXML.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Метод getSQLXML определен с помощью метода getSQLXML в интерфейсе java.sql.CallableStatement.  
  
## <a name="see-also"></a>См. также:  
 [Метод getSQLXML (SQLServerCallableStatement)](../../../connect/jdbc/reference/getsqlxml-method-sqlservercallablestatement.md)   
 [Члены SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)  
  
  
