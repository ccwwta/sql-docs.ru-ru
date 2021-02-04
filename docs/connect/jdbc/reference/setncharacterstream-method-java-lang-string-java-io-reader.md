---
description: Метод setNCharacterStream (java.lang.String, java.io.Reader)
title: Метод setNCharacterStream для объекта Reader (строка) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: fd19fbb8-a878-4d98-a584-e4969d649844
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 4eade5d22536d94a530d17b3060030986aba3aba
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99173337"
---
# <a name="setncharacterstream-method-javalangstring-javaioreader"></a>Метод setNCharacterStream (java.lang.String, java.io.Reader)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Задает указанному параметру заданный объект Reader.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public final void setNCharacterStream(java.lang.String parameterName,  
                       java.io.Reader value)  
```  
  
#### <a name="parameters"></a>Параметры  
 *parameterName*  
  
 Значение **String**, которое указывает имя параметра.  
  
 *value*  
  
 Объект Reader.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод setNCharacterStream задается с помощью метода setNCharacterStream в интерфейсе java.sql.CallableStatement.  
  
 Этот метод следует использовать для типов данных **NCHAR**, **NVARCHAR**, **NTEXT** и **XML**.  
  
## <a name="see-also"></a>См. также:  
 [Метод setNCharacterStream (SQLServerCallableStatement)](../../../connect/jdbc/reference/setncharacterstream-method-sqlservercallablestatement.md)   
 [Члены SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)  
  
  
