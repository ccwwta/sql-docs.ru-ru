---
description: Метод getSubString (SQLServerNClob)
title: Метод getSubString (SQLServerNClob) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: 1d91c930-1bac-4da9-b9a5-ac2cfd31541b
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 868bc1234c1f8f23b11b47967e5ae0d070191ccd
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99174910"
---
# <a name="getsubstring-method-sqlservernclob"></a>Метод getSubString (SQLServerNClob)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Извлекает копию указанной подстроки в **NCLOB** по указанной начальной позиции и числу символов для копирования.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public java.lang.String getSubString(long pos,  
                                  int length)  
```  
  
#### <a name="parameters"></a>Параметры  
 *pos*  
  
 Первый символ извлекаемой подстроки. Первый символ находится в позиции 1.  
  
 *length*  
  
 Количество копируемых последовательных символов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение **String**, указывающее подстроку в объекте **CLOB**.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getSubString определен с помощью метода getSubString в интерфейсе java.sql.NClob.  
  
 При попытке получения нулевых символов из NCLOB со значением NULK или с нулевой длиной возвращается пустая строка. При попытке получить длину символов, начиная с позиции, отличной от 1 (первой), для NCLOB нулевой длины возникнет исключение по позиции.  
  
## <a name="see-also"></a>См. также:  
 [Методы SQLServerNClob](../../../connect/jdbc/reference/sqlservernclob-methods.md)   
 [Элементы SQLServerNClob](../../../connect/jdbc/reference/sqlservernclob-members.md)   
 [Класс SQLServerNClob](../../../connect/jdbc/reference/sqlservernclob-class.md)  
  
  
