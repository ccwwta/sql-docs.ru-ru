---
description: Метод getApplicationName (SQLServerDataSource)
title: Метод getApplicationName (SQLServerDataSource) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerDataSource.getApplicationName
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: f71e501c-ccd7-4a1e-b6ea-4d47a81c18c6
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 45e4ce6a37e24ee4d3e8692fe4b145e8e8f019b6
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99168422"
---
# <a name="getapplicationname-method-sqlserverdatasource"></a>Метод getApplicationName (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает имя приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public java.lang.String getApplicationName()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение типа **String**, содержащее имя приложения или строку "[!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]", если значение не задано.  
  
## <a name="remarks"></a>Remarks  
 Имя приложения используется для идентификации определенных приложений в различных средствах профилирования и ведения журналов [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Если имя приложения не задано, метод getApplicationName возвращает нелокализованную строку "[!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]".  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Класс SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
