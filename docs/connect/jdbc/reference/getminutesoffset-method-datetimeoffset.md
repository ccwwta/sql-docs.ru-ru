---
description: Метод getMinutesOffset (DateTimeOffset)
title: Метод getMinutesOffset (DateTimeOffset) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: 18ba844a-ea36-42de-87da-bbc222082efe
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 44fe6c4be49cc8896ee1f59e3794617e839d8744
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99175467"
---
# <a name="getminutesoffset-method-datetimeoffset"></a>Метод getMinutesOffset (DateTimeOffset)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает смещение в минутах относительно времени GMT для данного объекта DateTimeOffset.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public int getMinutesOffset()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Смещение в минутах.  
  
## <a name="remarks"></a>Remarks  
 Для объекта DateTimeOffset, представляющего 8 марта 2010 г., 11:35:48 -0800, метод getMinutesOffset возвращает значение 480.  
  
## <a name="see-also"></a>См. также:  
 [Класс DateTimeOffset](../../../connect/jdbc/reference/datetimeoffset-class.md)   
 [Элементы DateTimeOffset](../../../connect/jdbc/reference/datetimeoffset-members.md)  
  
  
