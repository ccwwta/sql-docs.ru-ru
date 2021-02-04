---
description: Метод getCatalog (SQLServerConnection)
title: Метод getCatalog (SQLServerConnection) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerConnection.getCatalog
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: e87ef65f-4b5a-4e1c-8db5-7f0932390bb0
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: aba85b17bade5d9221a22dc98babf0c80b2853ab
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99165551"
---
# <a name="getcatalog-method-sqlserverconnection"></a>Метод getCatalog (SQLServerConnection)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает текущее имя каталога для объекта [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public java.lang.String getCatalog()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение типа **String**, содержащее имя каталога.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getCatalog определен с помощью метода getCatalog в интерфейсе java.sql.Connection.  
  
 Возвращает текущее свойство каталога для объекта SQLServerConnection или значение NULL, если свойство не задано. Свойство каталога задается явным методом [setCatalog](../../../connect/jdbc/reference/setcatalog-method-sqlserverconnection.md) или обновляется неявно при считывании изменения для переменной среды в потоке табличных данных для текущего каталога.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [Класс SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
