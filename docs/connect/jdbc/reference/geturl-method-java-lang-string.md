---
description: Метод getURL (java.lang.String)
title: Метод getURL (java.lang.String) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerCallableStatement.getURL (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: eb709f6b-64e1-4d0c-a704-290891627dd7
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: b0f24b28728673226bcddb3e77e3f97218aabd56
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99154685"
---
# <a name="geturl-method-javalangstring"></a>Метод getURL (java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Извлекает значение назначенного параметра в виде объекта URL на языке программирования Java по заданному имени параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public java.net.URL getURL(java.lang.String s)  
```  
  
#### <a name="parameters"></a>Параметры  
 *s*  
  
 Значение типа **String**, содержащее имя параметра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект URL.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getURL определен с помощью метода getURL в интерфейсе java.sql.CallableStatement.  
  
## <a name="see-also"></a>См. также:  
 [Метод getURL (SQLServerCallableStatement)](../../../connect/jdbc/reference/geturl-method-sqlservercallablestatement.md)   
 [Элементы SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [Класс SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  
