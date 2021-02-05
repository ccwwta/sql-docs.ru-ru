---
description: Метод getNClob (int)
title: Метод getNClob (int) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: 10dfa251-9408-469e-ae2a-1acf3917cf47
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 4cfd906b2b109d2785c016e82971f289622c1bec
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99175395"
---
# <a name="getnclob-method-int"></a>Метод getNClob (int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Извлекает значение указанного параметра JDBC **NCLOB** в виде объекта NClob на языке программирования Java.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public java.sql.NClob getNClob(int parameterIndex)  
```  
  
#### <a name="parameters"></a>Параметры  
 *parameterIndex*  
  
 Значение типа **int**, указывающее индекс параметра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект NClob.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getNClob определен с помощью метода getNClob в интерфейсе java.sql.CallableStatement.  
  
 Этот метод поддерживает только получение параметров **NCHAR**, **NVARCHAR**, **NTEXT** и **XML**. Вызов этих методов для других типов данных приведет к возникновению исключения.  
  
## <a name="see-also"></a>См. также:  
 [Метод getNClob (SQLServerCallableStatement)](../../../connect/jdbc/reference/getnclob-method-sqlservercallablestatement.md)   
 [Члены SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)  
  
  
