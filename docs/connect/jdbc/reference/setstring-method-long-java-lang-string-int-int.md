---
description: Метод setString (long, java.lang.String, int, int)
title: Метод setString (long, java.lang.String, int, int) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerClob.setString (long, java.lang.String, int, int)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 9fb59b09-e825-46a6-ba5d-85d4a8dc143a
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 1084ba6293ec6fa8056306558ec4d463848f312e
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99173046"
---
# <a name="setstring-method-long-javalangstring-int-int"></a>Метод setString (long, java.lang.String, int, int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Записывает заданную строку в объект CLOB, начиная с заданной позиции, по заданному смещению и длине.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public int setString(long pos,  
                     java.lang.String str,  
                     int offset,  
                     int len)  
```  
  
#### <a name="parameters"></a>Параметры  
 *pos*  
  
 Позиция, с которой начинается запись в объект CLOB.  
  
 *str*  
  
 Строка для записи в объект CLOB.  
  
 *offset*  
  
 Смещение в строке, с которого начинается считывание символов.  
  
 *len*  
  
 Количество записываемых символов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Количество записанных символов.  
  
## <a name="exceptions"></a>Исключения  
 java.sql.SQLException  
  
## <a name="remarks"></a>Remarks  
 Этот метод setString определен с помощью метода setString в интерфейсе java.sql.Clob.  
  
 Символьные данные перезаписываются, начиная с указанной позиции, и могут превысить исходную длину объекта CLOB. Если указать значение позиции+1, будет добавлена строка. Если указать значение позиции+2 и более (либо нулевое или отрицательное значение), то создается ошибка позиции.  
  
## <a name="see-also"></a>См. также:  
 [Метод setString (SQLServerClob)](../../../connect/jdbc/reference/setstring-method-sqlserverclob.md)   
 [Методы SQLServerClob](../../../connect/jdbc/reference/sqlserverclob-methods.md)   
 [Элементы SQLServerClob](../../../connect/jdbc/reference/sqlserverclob-members.md)   
 [Класс SQLServerClob](../../../connect/jdbc/reference/sqlserverclob-class.md)  
  
  
