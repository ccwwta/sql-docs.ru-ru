---
description: Метод getDisableStatementPooling (SQLServerDataSource)
title: Метод getDisableStatementPooling (SQLServerDataSource) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: ''
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 77bcc26fd02a63af1d002fcbe959af68e3f2e634
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99175874"
---
# <a name="getdisablestatementpooling-method-sqlserverdatasource"></a>Метод getDisableStatementPooling (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает значение свойства **disableStatementPooling** для подключения. Этот параметр определяет, включено ли объединение инструкций в пул для этого подключения.

  
## <a name="syntax"></a>Синтаксис  
  
```
public boolean getDisableStatementPooling();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 **Логическое** значение, которое содержит свойство подключения **disableStatementPooling**.
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
 
## <a name="remarks"></a>Remarks  
 Этот метод доступен в драйвере JDBC 6.4 и более поздних версий.
 
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Класс SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
