---
description: Метод getBytes (int)
title: Метод getBytes (int) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerCallableStatement.getBytes (int)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 8c2973e6-d57f-4f64-b812-350ce4098ce6
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: ebd8f927f977d2c243c8e78968796f669da5a424
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99165576"
---
# <a name="getbytes-method-int"></a>Метод getBytes (int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Получает значение указанного параметра в виде массива байтов по заданному индексу параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public byte[] getBytes(int index)  
```  
  
#### <a name="parameters"></a>Параметры  
 *index*  
  
 Значение типа **int**, указывающее индекс параметра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Массив значений типа **byte**.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 В предыдущей версии [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] метод SQLServerCallableStatement.getBytes мог преобразовывать значения из байтового массива в типы данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]**date**, **time**, **datetime2** или **datetimeoffset** и обратно. Теперь при вызове этого метода с такими типами данных возникает исключение, указывающее, что такое преобразование не поддерживается.  
  
 Этот метод getBytes определен с помощью метода getBytes в интерфейсе java.sql.CallableStatement.  
  
## <a name="see-also"></a>См. также:  
 [Метод getBytes (SQLServerCallableStatement)](../../../connect/jdbc/reference/getbytes-method-sqlservercallablestatement.md)   
 [Класс SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  
