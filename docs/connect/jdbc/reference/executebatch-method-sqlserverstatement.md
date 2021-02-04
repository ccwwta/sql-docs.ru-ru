---
description: Метод executeBatch (SQLServerStatement)
title: Метод executeBatch (SQLServerStatement) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerStatement.executeBatch
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: fb034f63-2532-4da8-a1b0-bc125734585a
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 43e92125d4a6503d2d093b12f7c0f7c59b00096d
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99165917"
---
# <a name="executebatch-method-sqlserverstatement"></a>Метод executeBatch (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Отправляет пакет команд базе данных для выполнения. В случае успешного выполнения всех команд возвращает массив из количества операций обновления, выполненных той или иной командой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public int[] executeBatch()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Массив значений **int**, содержащий счетчики обновлений.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
 java.sql.BatchUpdateException  
  
## <a name="remarks"></a>Remarks  
 Этот метод executeBatch определен с помощью метода executeBatch в интерфейсе java.sql.Statement.  
  
 После отправки команд в базу данных этот метод очищает все команды в пакете.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [Класс SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
