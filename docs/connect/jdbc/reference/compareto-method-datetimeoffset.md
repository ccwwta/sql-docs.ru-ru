---
description: Метод compareTo (DateTimeOffset)
title: Метод compareTo (DateTimeOffset) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: e4cf2ea4-0fe9-40ce-ba79-f2a2b616997e
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 02e36e2e64a6a628fd088fab448b30ea0c238450
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99176238"
---
# <a name="compareto-method-datetimeoffset"></a>Метод compareTo (DateTimeOffset)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Сравнивает данный объект **DateTimeOffset** с другим объектом **DateTimeOffset** по критерию совпадения времени GMT.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public int compareTo(DateTimeOffset other)  
```  
  
#### <a name="parameters"></a>Параметры  
 Значение [DateTimeOffset](../../../connect/jdbc/reference/datetimeoffset-class.md), которое нужно сравнить с текущим экземпляром.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В следующей таблице описывается значение, возвращаемое данным методом.  
  
|Возвращаемое значение|Описание|  
|------------------|-----------------|  
|0|Оба объекта **DateTimeOffset** представляют одну и ту же точку во времени.|  
|Отрицательное число|Данный объект **DateTimeOffset** представляет точку во времени, предшествующую *другому объекту*.|  
|Положительное число|Данный объект **DateTimeOffset** представляет точку во времени позднее *другого объекта*.|  
  
## <a name="remarks"></a>Remarks  
 Если два объекта **DateTimeOffset** имеют одно и то же время GMT, то дополнительное упорядочение объектов по смещению не производится.  
  
## <a name="see-also"></a>См. также:  
 [Класс DateTimeOffset](../../../connect/jdbc/reference/datetimeoffset-class.md)   
 [Элементы DateTimeOffset](../../../connect/jdbc/reference/datetimeoffset-members.md)  
  
  
