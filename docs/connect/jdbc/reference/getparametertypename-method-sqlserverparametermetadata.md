---
description: Метод getParameterTypeName (SQLServerParameterMetaData)
title: Метод getParameterTypeName (SQLServerParameterMetaData) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerParameterMetaData.getParameterTypeName
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: ebe7ff0f-3cc0-408e-9503-4ca754c9c37f
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 35f23e8f8364ddb49add56f27d29e7916438acda
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99162519"
---
# <a name="getparametertypename-method-sqlserverparametermetadata"></a>Метод getParameterTypeName (SQLServerParameterMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает имя определяемого базой данных типа для указанного параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public java.lang.String getParameterTypeName(int param)  
```  
  
#### <a name="parameters"></a>Параметры  
 *param*  
  
 Значение **int**, указывающее индекс параметра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение **String**, содержащее имя типа.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getParameterTypeName задается с помощью метода getParameterTypeName в интерфейсе java.sql.ParameterMetaData.  
  
## <a name="see-also"></a>См. также:  
 [Методы SQLServerParameterMetaData](../../../connect/jdbc/reference/sqlserverparametermetadata-methods.md)   
 [Элементы SQLServerParameterMetaData](../../../connect/jdbc/reference/sqlserverparametermetadata-members.md)   
 [Класс SQLServerParameterMetaData Class](../../../connect/jdbc/reference/sqlserverparametermetadata-class.md)  
  
  
