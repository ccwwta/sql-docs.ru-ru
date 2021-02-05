---
title: Класс SQLServerConnection
description: Узнайте об общедоступном API-интерфейсе для класса SQLServerConnection в драйвере JDBC для SQL Server.
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: 937292a6-1525-423e-a2b2-a18fd34c2893
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: df6b46047ed99b93d0baf45ea8a8a4f28721b875
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99178374"
---
# <a name="sqlserverconnection-class"></a>Класс SQLServerConnection
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Представляет соединение JDBC с базой данных [!INCLUDE[msCoName](../../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
 **Пакет:** com.microsoft.sqlserver.jdbc  
  
 **Реализует:** [ISQLServerConnection](../../../connect/jdbc/reference/isqlserverconnection-interface.md), java.io.Serializable  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public class SQLServerConnection  
```  
  
## <a name="remarks"></a>Remarks  
 SQLServerConnection поддерживает пулы соединений JDBC и может быть физическим или логическим подключением JDBC. SQLServerConnection управляет транзакциями для всех инструкций, созданных из него, и может участвовать в распределенных транзакциях XA, управляемых с помощью адаптера XAResource.  
  
 SQLServerConnection управляет пулом дескрипторов подготовленных инструкций. Подготовленные инструкции готовятся один раз и обычно выполняются несколько раз с различными значениями параметров. Кроме того, подготовленные транзакции сохраняются после закрытия логических соединений (входящих в пул).  
  
> [!NOTE]  
>  SQLServerConnection не является потокобезопасным. Однако несколько инструкций, созданных из одного соединения, можно обрабатывать одновременно в параллельных потоках.  
  
 Этот класс поддерживает распаковку в класс SQLServerConnection, интерфейс java.sql.connection и интерфейс ISQLServerConnection. См. сведения об [интерфейсах и программах-оболочках](../../../connect/jdbc/wrappers-and-interfaces.md).  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [Справка по API драйвера JDBC](../../../connect/jdbc/reference/jdbc-driver-api-reference.md)  
  
  
