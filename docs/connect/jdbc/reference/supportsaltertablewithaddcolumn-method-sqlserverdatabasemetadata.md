---
description: Метод supportsAlterTableWithAddColumn (SQLServerDatabaseMetaData)
title: Метод supportsAlterTableWithAddColumn | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerDatabaseMetaData.supportsAlterTableWithAddColumn
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: bbac1370-fbf6-4450-8599-4ed3b4db3fc6
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 8e3118991cbd47f31dfb64a2d95d50943bd446df
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99111120"
---
# <a name="supportsaltertablewithaddcolumn-method-sqlserverdatabasemetadata"></a>Метод supportsAlterTableWithAddColumn (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает значение, определяющее, поддерживает ли эта база данных инструкцию ALTER TABLE с добавлением столбца.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public boolean supportsAlterTableWithAddColumn()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 **true**, если поддерживается. В противном случае — **false**.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод supportsAlterTableWithAddColumn задается с помощью метода supportsAlterTableWithAddColumn в интерфейсе java.sql.DatabaseMetaData.  
  
## <a name="see-also"></a>См. также:  
 [Методы SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [Элементы SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [Класс SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
