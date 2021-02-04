---
description: Метод isWrapperFor (SQLServerStatement)
title: Метод isWrapperFor (SQLServerStatement) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: 53f3291f-d43a-476b-a656-d86168dacf6c
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 6b2cb6fe67d9a2ec5cbb0c56c5e1d1c3573533ef
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99177132"
---
# <a name="iswrapperfor-method-sqlserverstatement"></a>Метод isWrapperFor (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Указывает, является ли этот объект инструкции оболочкой указанного интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public boolean isWrapperFor(Class iface)  
```  
  
#### <a name="parameters"></a>Параметры  
 *iface*  
  
 **Класс**, определяющий интерфейс.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если этот объект реализует интерфейс или упаковывает объект, реализующий интерфейс. В противном случае — **false**.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Метод [isWrapperFor](../../../connect/jdbc/reference/iswrapperfor-method-sqlserverstatement.md) и метод [unwrap](../../../connect/jdbc/reference/unwrap-method-sqlserverstatement.md) определяются интерфейсом java.sql.Wrapper, представленного в JDBC 4.0.  
  
 Если этот метод возвращает значение true, вызов метода [unwrap](../../../connect/jdbc/reference/unwrap-method-sqlserverstatement.md) с таким же аргументом будет выполнен успешно.  
  
 Пример кода можно найти в статье с [примером обновления большого объема данных](../../../connect/jdbc/updating-large-data-sample.md).  
  
 См. сведения об [интерфейсах и программах-оболочках](../../../connect/jdbc/wrappers-and-interfaces.md).  
  
## <a name="see-also"></a>См. также:  
 [Метод unwrap (SQLServerStatement)](../../../connect/jdbc/reference/unwrap-method-sqlserverstatement.md)   
 [Элементы SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [Класс SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
