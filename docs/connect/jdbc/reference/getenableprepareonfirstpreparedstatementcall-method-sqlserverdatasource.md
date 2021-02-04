---
description: Метод getEnablePrepareOnFirstPreparedStatementCall (SQLServerDataSource)
title: Метод getEnablePrepareOnFirstPreparedStatementCall (SQLServerDataSource) | Документация Майкрософт
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
ms.openlocfilehash: 266a9094e55c8ea239bf3a9997aa684042c84b76
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99163070"
---
# <a name="getenableprepareonfirstpreparedstatementcall-method-sqlserverdatasource"></a>Метод getEnablePrepareOnFirstPreparedStatementCall (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает значение свойства подключения **enablePrepareOnFirstPreparedStatementCall**. Если эта конфигурация возвращает значение false, то первое выполнение подготовленной инструкции вызовет sp_executesql без подготовки инструкции, после второго выполнения будет вызван sp_prepexec и фактически настроен обработчик подготовленной инструкции. При всех последующих выполнениях вызывается sp_execute. Это избавляет от необходимости аннулировать закрываемую подготовленную инструкцию вызовом sp_unprepare, если эта инструкция выполнялась лишь один раз. 
  
## <a name="syntax"></a>Синтаксис  
  
```
public boolean getEnablePrepareOnFirstPreparedStatementCall();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает **логическое** значение свойства подключения **enablePrepareOnFirstPreparedStatementCall**.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
 
## <a name="remarks"></a>Remarks  
 Этот метод доступен в драйвере JDBC 6.4 и более поздних версий.
 
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Класс SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
