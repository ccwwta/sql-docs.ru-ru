---
description: Метод moveToInsertRow (SQLServerResultSet)
title: Метод moveToInsertRow (SQLServerResultSet) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerResultSet.moveToInsertRow
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: f3c54bfe-d5b7-4f6e-ae6c-3e8954e5b1c9
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 431e9dbc8570d9505b9a2bfd1b8922229b22e3e1
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99177037"
---
# <a name="movetoinsertrow-method-sqlserverresultset"></a>Метод moveToInsertRow (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Перемещает курсор в строку вставки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public void moveToInsertRow()  
```  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод moveToInsertRow задается с помощью метода moveToInsertRow в интерфейсе java.sql.ResultSet.  
  
 Текущая позиция курсора запоминается, пока курсор располагается в строке вставки. Строка вставки — это специальная строка, связанная с обновляемым результирующим набором. Фактически она служит буфером, в котором можно создать новую строку, вызывая методы обновления, перед добавлением строки в результирующий набор.  
  
 Пока курсор находится в строке вставки, можно вызывать только метод обновления, метод считывания и метод [insertRow](../../../connect/jdbc/reference/insertrow-method-sqlserverresultset.md). При каждом вызове этого метода и перед вызовом метода insertRow всем столбцам в результирующем наборе должны присваиваться значения. Метод обновления должен вызываться перед вызовом метода считывания для значения столбца.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Класс SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
