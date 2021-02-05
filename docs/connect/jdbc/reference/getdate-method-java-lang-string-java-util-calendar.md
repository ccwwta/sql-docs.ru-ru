---
description: Метод getDate (java.lang.String, java.util.Calendar)
title: Метод getDate (java.util.Calendar) — параметр | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerCallableStatement.getDate (java.util.Calendar)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 6d0deaf2-6f12-4a6e-b537-a51fa3478059
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 2be9ea1fc68f7771b5983032dbbe29de47899915
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99175954"
---
# <a name="getdate-method-javalangstring-javautilcalendar"></a>Метод getDate (java.lang.String, java.util.Calendar)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Получает значение указанного параметра в виде объекта java.sql.Date на языке программирования Java по заданному имени параметра и объекту Calendar.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public java.sql.Date getDate(java.lang.String sCol,  
                             java.util.Calendar cal)  
```  
  
#### <a name="parameters"></a>Параметры  
 *sCol*  
  
 Значение типа **String**, содержащее имя параметра.  
  
 *cal*  
  
 Объект Calendar.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект Date.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getDate указывается методом getDate в интерфейсе java.sql.CallableStatement.  
  
 Этот метод возвращает допустимую часть даты для типа данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] datetime или smalldatetime, а часть времени имеет начальное значение времени Java — 00:00 (полночь).  
  
## <a name="see-also"></a>См. также:  
 [Метод getDate (SQLServerCallableStatement)](../../../connect/jdbc/reference/getdate-method-sqlservercallablestatement.md)   
 [Элементы SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [Класс SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  
