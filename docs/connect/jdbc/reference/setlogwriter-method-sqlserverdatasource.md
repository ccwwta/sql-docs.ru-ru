---
description: Метод setLogWriter (SQLServerDataSource)
title: Метод setLogWriter (SQLServerDataSource) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerDataSource.setLogWriter
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 7a77d8ef-2211-4bf8-af35-020fc896c073
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: ed4dca734759cfc5fd1d2f67bd3f2feecf9ae8b5
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99178887"
---
# <a name="setlogwriter-method-sqlserverdatasource"></a>Метод setLogWriter (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Этот метод предназначен только для внутреннего использования. Дополнительные сведения о ведении журнала см. в статье о [трассировке операций драйвера](../../../connect/jdbc/tracing-driver-operation.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public void setLogWriter(java.io.PrintWriter out)  
```  
  
#### <a name="parameters"></a>Параметры  
 *out*  
  
 Объект PrintWriter.  
  
## <a name="remarks"></a>Комментарии  
 Этот метод setLogWriter задается с помощью метода setLogWriter в интерфейсе javax.sql.DataSource.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Класс SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
