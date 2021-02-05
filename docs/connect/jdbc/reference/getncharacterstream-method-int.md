---
description: Метод getNCharacterStream (int)
title: Метод getNCharacterStream (int) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: 6ae704f5-823c-4dfe-8c08-07b547c61a3c
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 2d32325349d63d1dbc4633e97ea7c4aebfd3dc56
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99175441"
---
# <a name="getncharacterstream-method-int"></a>Метод getNCharacterStream (int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает значение указанного параметра в виде объекта Reader по индексу параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public final java.io.Reader getNCharacterStream(int parameterIndex)  
```  
  
#### <a name="parameters"></a>Параметры  
 *parameterIndex*  
  
 Значение типа **int**, указывающее индекс параметра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект Reader.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод должен использоваться при доступе к параметрам **NCHAR**, **NVARCHAR** и **LONGNVARCHAR**.  
  
 Этот метод getNCharacterStream задается с помощью метода getNCharacterStream в интерфейсе java.sql.CallableStatement.  
  
## <a name="see-also"></a>См. также:  
 [Метод getNCharacterStream (SQLServerCallableStatement)](../../../connect/jdbc/reference/getncharacterstream-method-sqlservercallablestatement.md)   
 [Члены SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)  
  
  
