---
description: Класс SQLServerConnectionPoolDataSource
title: Класс SQLServerConnectionPoolDataSource | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: b00e5a90-2af7-4d04-8ef8-256183777dcf
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 152dcc1f6aa2d8b463b3e859f79ade54b5620334
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99172832"
---
# <a name="sqlserverconnectionpooldatasource-class"></a>Класс SQLServerConnectionPoolDataSource
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Представляет физические подключение к базе данных для диспетчеров пулов соединений.  
  
 **Пакет:** com.microsoft.sqlserver.jdbc  
  
 **Расширение:** [SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
 **Реализует:** javax.sql.ConnectionPoolDataSource  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public class SQLServerConnectionPoolDataSource  
```  
  
## <a name="remarks"></a>Remarks  
 SQLServerConnectionPoolDataSource обычно используется в средах Java Application Server, поддерживающих встроенные пулы соединений и требующих для установки физических соединений объект ConnectionPoolDataSource, например на серверах приложений платформы Java Enterprise Edition (Java EE), которые обеспечивают организацию пулов соединений по спецификациям JDBC 3.0 API.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerConnectionPoolDataSource](../../../connect/jdbc/reference/sqlserverconnectionpooldatasource-members.md)   
 [Справка по API драйвера JDBC](../../../connect/jdbc/reference/jdbc-driver-api-reference.md)  
  
  
