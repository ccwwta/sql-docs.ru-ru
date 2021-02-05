---
description: Метод isSparseColumnSet (SQLServerResultSetMetaData)
title: Метод isSparseColumnSet (SQLServerResultSetMetaData) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: ac363670-78ae-49f1-aeda-4fba3329a258
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 7d84f7d53f3b8040e2d126eb6166bc211d97a770
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99177212"
---
# <a name="issparsecolumnset-method-sqlserverresultsetmetadata"></a>Метод isSparseColumnSet (SQLServerResultSetMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Указывает, является ли столбец из результирующего набора набором разреженных столбцов.  
  
## <a name="syntax"></a>Синтаксис  
  
```scr  
public boolean isSparseColumnSet(int column)  
```  
  
#### <a name="parameters"></a>Параметры  
 *column*  
  
 Индекс столбца (начинающийся с единицы).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если столбец из результирующего набора является набором разреженных столбцов. В противном случае ― **false**.  
  
## <a name="remarks"></a>Remarks  
 Этот метод не извлекает данные из базы данных.  
  
## <a name="see-also"></a>См. также:  
 [Методы SQLServerResultSetMetaData](../../../connect/jdbc/reference/sqlserverresultsetmetadata-methods.md)   
 [Элементы SQLServerResultSetMetaData](../../../connect/jdbc/reference/sqlserverresultsetmetadata-members.md)   
 [Класс SQLServerResultSetMetaData](../../../connect/jdbc/reference/sqlserverresultsetmetadata-class.md)  
  
  
