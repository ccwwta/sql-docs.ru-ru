---
description: Метод executeUpdate (java.lang.String, java.lang.String)
title: Метод executeUpdate (java.lang.String, java.lang.String) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerStatement.executeUpdate (java.lang.String[])
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 2f44a689-65c8-4c94-9574-e9c08ea7918e
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 70adee8fbc97e487c2731a92e1c80fa6a4bff1be
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99163420"
---
# <a name="executeupdate-method-javalangstring-javalangstring"></a>Метод executeUpdate (java.lang.String, java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Выполняет заданную инструкцию SQL и сообщает драйверу [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] о том, что автоматически созданные ключи должны быть доступными для получения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public final int executeUpdate(java.lang.String sql,  
                               java.lang.String[] columnNames)  
```  
  
#### <a name="parameters"></a>Параметры  
 *sql*  
  
 Значение типа **String**, содержащее инструкцию SQL.  
  
 *columnNames*  
  
 Массив типа **String**, указывающий, какие имена столбцов автоматически созданных ключей должны быть доступными для извлечения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение **int**, которое указывает число затронутых строк, либо значение 0 для инструкции DDL.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод executeUpdate определен с помощью метода executeUpdate в интерфейсе java.sql.Statement.  
  
 Если в результате выполнения хранимой процедуры счетчик обновлений больше единицы либо сформировано больше одного результирующего набора, используйте для выполнения хранимой процедуры метод [execute](../../../connect/jdbc/reference/execute-method-sqlserverstatement.md).  
  
## <a name="see-also"></a>См. также:  
 [Метод executeUpdate &#40;SQLServerStatement&#41;](../../../connect/jdbc/reference/executeupdate-method-sqlserverstatement.md)   
 [Элементы SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [Класс SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
