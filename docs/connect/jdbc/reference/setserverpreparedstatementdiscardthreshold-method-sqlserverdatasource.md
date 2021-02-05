---
description: Метод setServerPreparedStatementDiscardThreshold (SQLServerDataSource)
title: Метод setServerPreparedStatementDiscardThreshold (SQLServerDataSource) | Документация Майкрософт
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
ms.openlocfilehash: 570b857b9e589fb71d791e47af90acca1927cfc5
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99173099"
---
# <a name="setserverpreparedstatementdiscardthreshold-method-sqlserverdatasource"></a>Метод setServerPreparedStatementDiscardThreshold (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Задает значение свойства подключения serverPreparedStatementDiscardThreshold. Этот параметр определяет, сколько невыполненных операций отмены для подготовленных инструкций (sp_unprepare) допускается для каждого подключения, прежде чем на сервере будет выполнен вызов очистки незавершенных обработчиков. Когда этот параметр имеет значение не более 1, действия аннулирования выполняются немедленно после завершения подготовленной инструкции. Если задано значение больше 1, эти вызовы объединяются в пакет, чтобы избежать накладных расходов на частый вызов sp_unprepare.
 
## <a name="syntax"></a>Синтаксис  
  
```
public void setServerPreparedStatementDiscardThreshold(int enablePrepareOnFirstPreparedStatementCall);  
```  
  
#### <a name="parameters"></a>Параметры  
 *serverPreparedStatementDiscardThreshold*  
  
 Новое значение свойства подключения **serverPreparedStatementDiscardThreshold**.  

## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
 
## <a name="remarks"></a>Remarks  
 Этот метод доступен в драйвере JDBC 6.4 и более поздних версий.
 
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Класс SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
