---
description: Метод supportsCoreSQLGrammar (SQLServerDatabaseMetaData)
title: Метод supportsCoreSQLGrammar (SQLServerDatabaseMetaData) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerDatabaseMetaData.supportsCoreSQLGrammar
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 6b82f300-f906-4d11-b810-525bda4a88ee
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 22dfa94029f5b76fa2b0ddfdd5c27af9ce592241
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99160908"
---
# <a name="supportscoresqlgrammar-method-sqlserverdatabasemetadata"></a>Метод supportsCoreSQLGrammar (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает значение, определяющее, поддерживает ли эта база данных базовую SQL-грамматику ODBC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public boolean supportsCoreSQLGrammar()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 **true**, если поддерживается. В противном случае — **false**.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод supportsCoreSQLGrammar указывается с помощью метода supportsCoreSQLGrammar в интерфейсе java.sql.DatabaseMetaData.  
  
## <a name="see-also"></a>См. также:  
 [Методы SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [Элементы SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [Класс SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
