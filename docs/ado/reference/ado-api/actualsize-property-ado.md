---
description: Свойство ActualSize (ADO)
title: Свойство ActualSize (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 03/20/2018
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Field20::ActualSize
helpviewer_keywords:
- ActualSize property [ADO]
ms.assetid: 722803d0-cef5-4d4c-b79d-3f2f58052229
author: rothja
ms.author: jroth
ms.openlocfilehash: 929d787d0d412a405f0df8d3a2377ae8a1493586
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99161789"
---
# <a name="actualsize-property-ado"></a>Свойство ActualSize (ADO)
Указывает фактическую длину значения поля в байтах.  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Возвращает значение **типа Long** .  
  
## <a name="remarks"></a>Замечания  
 Используйте свойство **ActualSize** , чтобы вернуть фактическую длину значения объекта [поля](./field-object.md) . Для всех полей свойство **ActualSize** доступно только для чтения. Если ADO не удается определить длину значения объекта **поля** , свойство **ActualSize** возвращает **адункновн**.  
  
 Свойства **ActualSize** и [DefinedSize](./definedsize-property.md) различаются, как показано в следующем примере. Объект **поля** с объявленным типом **адварчар** и максимальной длиной 50 символов возвращает значение свойства **DefinedSize** , равное 50, но возвращаемое значение свойства **ActualSize** — это длина данных, хранящихся в поле для текущей записи. **Поля** с **DefinedSize** размером более 255 байт рассматриваются как столбцы переменной длины.  
  
## <a name="applies-to"></a>Применение  
 [Объект Field](./field-object.md)  
  
## <a name="see-also"></a>См. также:  
 [Примеры свойств ActualSize и DefinedSize (Visual Basic)](./actualsize-and-definedsize-properties-example-vb.md)   
 [Пример свойств ActualSize и DefinedSize (Visual c++)](./actualsize-and-definedsize-properties-example-vc.md)   
 [Свойство DefinedSize](./definedsize-property.md)