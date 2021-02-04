---
description: Метод getParameterCount (SQLServerParameterMetaData)
title: Метод getParameterCount (SQLServerParameterMetaData) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerParameterMetaData.getParameterCount
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 7dbbdacb-74ef-42e7-9bdc-a3229505dad8
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: bc586f7b36f09f7accd370bda6e34d8ef571aee2
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99162552"
---
# <a name="getparametercount-method-sqlserverparametermetadata"></a>Метод getParameterCount (SQLServerParameterMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает число параметров в объекте [SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md), для которого объект [SQLServerParameterMetaData](../../../connect/jdbc/reference/sqlserverparametermetadata-class.md) содержит данные.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public int getParameterCount()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение **int**, указывающее количество параметров.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getParameterCount задается с помощью метода getParameterCount в интерфейсе java.sql.ParameterMetaData.  
  
## <a name="see-also"></a>См. также:  
 [Методы SQLServerParameterMetaData](../../../connect/jdbc/reference/sqlserverparametermetadata-methods.md)   
 [Элементы SQLServerParameterMetaData](../../../connect/jdbc/reference/sqlserverparametermetadata-members.md)   
 [Класс SQLServerParameterMetaData Class](../../../connect/jdbc/reference/sqlserverparametermetadata-class.md)  
  
  
