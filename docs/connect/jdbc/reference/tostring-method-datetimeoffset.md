---
description: Метод toString (DateTimeOffset)
title: Метод toString (DateTimeOffset) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: e77b9be3-1a02-4769-8acf-ac71d48d6a76
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 4599b8152bbb7041565cc4858199ec88d1bb0510
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99158831"
---
# <a name="tostring-method-datetimeoffset"></a>Метод toString (DateTimeOffset)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает строковое представление текущего объекта **DateTimeOffset**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public String toString()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Строковое представление текущего объекта **DateTimeOffset**.  
  
## <a name="remarks"></a>Remarks  
 Эта строка имеет формат `YYYY-MM-DD HH:mm:ss[.fffffff] [+|-]HH:mm`.  
  
 Доли секунды возвращаемой строки дополняются нулями до объявленной точности. Например, **DateTimeOffset (6)** со значением "2010-03-10 12:34:56.78 -08:00" при выполнении DateTimeOffset.toStringбудет отформатировано как "2010-03-10 12:34:56.780000 -08:00".  
  
## <a name="see-also"></a>См. также:  
 [Класс DateTimeOffset](../../../connect/jdbc/reference/datetimeoffset-class.md)   
 [Элементы DateTimeOffset](../../../connect/jdbc/reference/datetimeoffset-members.md)  
  
  
