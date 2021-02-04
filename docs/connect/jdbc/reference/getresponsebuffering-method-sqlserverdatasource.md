---
description: Метод getResponseBuffering (SQLServerDataSource)
title: Метод getResponseBuffering (SQLServerDataSource) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerDataSource.getResponseBuffering()
apilocation:
- SQLServerDataSource.getResponseBuffering()
apitype: Assembly
ms.assetid: 19585a93-88a4-415e-a20e-12ba58cddeaa
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 0162e8aa1b4adcd83cbb4226edd67464fa7fd7d4
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99162435"
---
# <a name="getresponsebuffering-method-sqlserverdatasource"></a>Метод getResponseBuffering (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает режим буферизации ответов для этого объекта [SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public java.lang.String getResponseBuffering()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 **Строка** со значением **full** или **adaptive** в нижнем регистре.  
  
## <a name="remarks"></a>Remarks  
 Значение **full** указывает на чтение всех результатов с сервера во время выполнения.  
  
 Значение **adaptive** указывает на буферизацию минимального количества данных при необходимости. Значение **adaptive** — это режим буферизации по умолчанию.  
  
 Дополнительные сведения об использовании режима буферизации ответов см. в статье [Использование адаптивной буферизации](../../../connect/jdbc/using-adaptive-buffering.md).  
  
## <a name="see-also"></a>См. также:  
 [Метод setResponseBuffering (SQLServerDataSource)](../../../connect/jdbc/reference/setresponsebuffering-method-sqlserverdatasource.md)   
 [Элементы SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Класс SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
