---
description: Метод getPacketSize (SQLServerDataSource)
title: Метод getPacketSize (SQLServerDataSource) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerDataSource.getPacketSize
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: b2e9f01a-2e51-47e5-90bf-43c62d1be74d
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 1fb42a8d875cd3e3e72eebc212a8050a41e389b6
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99162582"
---
# <a name="getpacketsize-method-sqlserverdatasource"></a>Метод getPacketSize (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает текущий размер сетевого пакета в байтах, используемый для обмена данными с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public int getPacketSize()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение типа **int**, содержащее текущий размер сетевого пакета.  
  
## <a name="remarks"></a>Комментарии  
 Если свойство packetSize не задано, метод getPacketSize возвращает значение по умолчанию (8000).  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Класс SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
