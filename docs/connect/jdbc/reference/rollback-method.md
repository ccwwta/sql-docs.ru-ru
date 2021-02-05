---
description: Метод rollback ()
title: Метод rollback () | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerConnection.rollback ()
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 7adb6772-4047-4d8e-931d-b3d20eec44b5
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: cc5f37ecd5965600a68a3df7dbdb3484fd6b6658
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99174092"
---
# <a name="rollback-method-"></a>Метод rollback ()
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Отменяет все изменения, сделанные в текущей транзакции, и снимает в базе данных все блокировки, удерживаемые данным объектом [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public void rollback()  
```  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод rollBack определен с помощью метода rollBack в интерфейсе java.sql.Connection.  
  
 Этот метод следует использовать, только если отключен режим автоматической фиксации.  
  
## <a name="see-also"></a>См. также:  
 [rollback Method &#40;SQLServerConnection&#41;](../../../connect/jdbc/reference/rollback-method-sqlserverconnection.md)  (Метод rollback (SQLServerConnection))  
 [Элементы SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [Класс SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
