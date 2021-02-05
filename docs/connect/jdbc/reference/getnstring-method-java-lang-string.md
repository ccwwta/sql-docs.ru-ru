---
description: Метод getNString (java.lang.String)
title: Метод getNString (java.lang.String) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: b351e999-85bf-498b-915a-f91d89134bce
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 403b7117b4bc1bb4f8ceca95e665ed10aee98279
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99175321"
---
# <a name="getnstring-method-javalangstring"></a>Метод getNString (java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Извлекает значение указанного параметра **NCHAR**, **NVARCHAR** или **LONGNVARCHAR** в виде значения String на языке программирования Java.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public final java.lang.String getNString(java.lang.String parameterName)  
```  
  
#### <a name="parameters"></a>Параметры  
 *parameterName*  
  
 Значение типа **String**, содержащее имя параметра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект String.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getString определен с помощью метода getString в интерфейсе java.sql.CallableStatement.  
  
## <a name="see-also"></a>См. также:  
 [Метод getNString (SQLServerCallableStatement)](../../../connect/jdbc/reference/getnstring-method-sqlservercallablestatement.md)   
 [Методы SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-methods.md)  
  
  
