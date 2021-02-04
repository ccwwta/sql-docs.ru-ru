---
description: Метод getReference (SQLServerDataSource)
title: Метод getReference (SQLServerDataSource) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerDataSource.getReference
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: b3fb1a97-86ee-4977-adca-c35ae199dbb3
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: d44e8f10c1e4160504d20de7d5a9b3e36b31b950
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99175211"
---
# <a name="getreference-method-sqlserverdatasource"></a>Метод getReference (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает ссылку на этот объект [SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public javax.naming.Reference getReference()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект Reference.  
  
## <a name="remarks"></a>Remarks  
 Этот метод getReference задается с помощью метода getReference в интерфейсе javax.naming.Referenceable.  
  
 Если в версиях драйвера [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] JDBC, предшествующих 3.0, метод SQLServerDataSource.setTrustStorePassword вызывался в объекте SQLServerDataSource, пароль присутствовал в объекте, возвращаемом SQLServerDataSource.getReference, что позволяло использовать объект для создания дополнительных соединений. В версии 3.0 драйвера JDBC необходимо установить пароль для объекта, возвращаемого SQLServerDataSource.getReference, перед установлением соединения с объектом.  
  
 Кроме того, если SQLServerDataSource.setTrustStorePassword задается перед привязкой свойств источника данных, необходимо вызвать метод SQLServerDataSource.setTrustStorePassword перед получением соединения. Например,  
  
```  
ctx = new InitialContext(System.getProperties());  
  
SQLServerDataSource ds1 = (SQLServerDataSource) ctx.lookup(jndiName);  
  
ds1.setTrustStorePassword("XXXXX");  
Connection con = ds1.getConnection("user", "XXXXXX");  
  
ctx.rebind(jndiName, ds1);  
SQLServerDataSource ds2 = (SQLServerDataSource) ctx.lookup(jndiName);  
ds2.setTrustStorePassword("XXXXX");   // reset the truststore password  
con = ds2.getConnection("user", "XXXXXX");   // provide userid and password again  
```  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Класс SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
