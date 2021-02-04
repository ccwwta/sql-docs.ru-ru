---
description: Метод clearWarnings (SQLServerResultSet)
title: Метод clearWarnings (SQLServerResultSet) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerResultSet.clearWarnings
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: f55af4b6-ae5c-41c9-8aa3-8313773f5443
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 2a1d364353ab3d0262adb1446686771a9811aa99
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99163503"
---
# <a name="clearwarnings-method-sqlserverresultset"></a>Метод clearWarnings (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Удаляет все предупреждения, включенные в отчет для этого объекта [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md).  
  
> [!NOTE]  
>  В настоящее время этот метод не реализуется драйвером [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]. При вызове он всегда возвращает значение NULL.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public void clearWarnings()  
```  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод clearWarnings задается с помощью метода clearWarnings в интерфейсе java.sql.ResultSet.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Класс SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
