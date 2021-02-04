---
description: Метод getTime (int)
title: Метод getTime (int) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerCallableStatement.getTime (int)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 6c13dea2-511f-48dc-b3db-2d3b72ccc9de
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 7a0486a9816106b5ed07bcddf9a78a130bf24903
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99162154"
---
# <a name="gettime-method-int"></a>Метод getTime (int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Получает значение указанного параметра в виде объекта java.sql.Time на языке программирования Java по заданному индексу параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public java.sql.Time getTime(int index)  
```  
  
#### <a name="parameters"></a>Параметры  
 *index*  
  
 Значение типа **int**, указывающее индекс параметра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект Time.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getTime указывается методом getTime в интерфейсе java.sql.CallableStatement.  
  
 См. диаграмму с названием "Преобразования метода считывания" в статье с [основными сведениями о преобразованиях типов данных](../../../connect/jdbc/understanding-data-type-conversions.md), чтобы узнать, какие типы данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] можно извлечь с использованием этого метода.  
  
## <a name="see-also"></a>См. также:  
 [Метод getTime (SQLServerCallableStatement)](../../../connect/jdbc/reference/gettime-method-sqlservercallablestatement.md)   
 [Элементы SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [Класс SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  
