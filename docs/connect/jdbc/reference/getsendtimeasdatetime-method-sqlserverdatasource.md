---
description: Метод getSendTimeAsDatetime (SQLServerDataSource)
title: Метод getSendTimeAsDatetime (SQLServerDataSource) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: 02287122-5dc1-455d-987f-95fd9a69d503
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: ba9fd31fdbc5626fc3baa81c853bc78ea2a81abc
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99175069"
---
# <a name="getsendtimeasdatetime-method-sqlserverdatasource"></a>Метод getSendTimeAsDatetime (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Этот метод добавлен в версии 3.0 драйвера [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] JDBC.  
  
 Возвращает значение свойства подключения **sendTimeAsDatetime**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public boolean getSendTimeAsDatetime();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 **true**, если значения java.sql.Time будут отправляться на сервер с типом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] **datetime**. **false**, если значения java.sql.Time будут отправляться на сервер с типом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] **time**.  
  
## <a name="remarks"></a>Remarks  
 Дополнительные сведения о свойстве подключения [sendTimeAsDatetime](../../../connect/jdbc/setting-the-connection-properties.md) см. в статье о **настройке свойств подключения**.  
  
 [Метод SQLServerDataSource.setSendTimeAsDatetime](../../../connect/jdbc/reference/setsendtimeasdatetime-method-sqlserverdatasource.md) позволяет программным образом устанавливать свойство соединения **sendTimeAsDatetime**.  
  
 Дополнительные сведения см. в статье [Настройка способа отправки значений java.sql.Time на сервер](../../../connect/jdbc/configuring-how-java-sql-time-values-are-sent-to-the-server.md).  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Класс SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
