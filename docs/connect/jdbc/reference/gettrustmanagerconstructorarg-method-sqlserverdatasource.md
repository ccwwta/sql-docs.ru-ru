---
description: Метод getTrustManagerConstructorArg (SQLServerDataSource)
title: Метод getTrustManagerConstructorArg (SQLServerDataSource) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerDataSource.getTrustManagerConstructorArg
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: ''
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 41e3a4c86a5b5ad43a425614fab09d59a9d0340e
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99165475"
---
# <a name="gettrustmanagerconstructorarg-method-sqlserverdatasource"></a>Метод getTrustManagerConstructorArg (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает строковое значение свойства подключения TrustManagerConstructorArg.
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public java.lang.String getTrustManagerConstructorArg()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает **строковое** значение свойства подключения TrustManagerConstructorArg или NULL, если это свойство не имеет значения.  
  
## <a name="remarks"></a>Комментарии  
 Если свойство TrustManagerClass не задано, то метод [getTrustManagerConstructorArg](../../../connect/jdbc/reference/gettrustmanagerconstructorarg-method-sqlserverdatasource.md) возвращает значение NULL.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Класс SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
