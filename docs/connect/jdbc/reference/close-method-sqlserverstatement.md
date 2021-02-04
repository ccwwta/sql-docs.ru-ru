---
description: Метод close (SQLServerStatement)
title: Метод close (SQLServerStatement) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerStatement.close
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 84a25d64-dd3e-4696-bb5f-4eaf391fab7e
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 794c16e179fd7e2d68984248b0e833455eadd372
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99163478"
---
# <a name="close-method-sqlserverstatement"></a>Метод close (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Немедленно освобождает базу данных и ресурсы JDBC данного объекта [SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md), не дожидаясь их автоматического освобождения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public void close()  
```  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод close определен с помощью метода close в интерфейсе java.sql.Statement.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [Класс SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
