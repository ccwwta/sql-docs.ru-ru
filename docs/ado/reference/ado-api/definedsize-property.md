---
description: Свойство DefinedSize
title: DefinedSize, свойство | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Field20::DefinedSize
helpviewer_keywords:
- DefinedSize property [ADO]
ms.assetid: 3ee27314-a305-4fbc-8433-9ee9a909afd6
author: rothja
ms.author: jroth
ms.openlocfilehash: 756fe40bf7916dfa3e56a3e559be2874b5e8cd85
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99171310"
---
# <a name="definedsize-property"></a>Свойство DefinedSize
Указывает емкость данных для объекта [поля](../../../ado/reference/ado-api/field-object.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение типа **Long** , отражающее заданный размер поля, который зависит от типов данных объекта Field. Дополнительные сведения см. в разделе [тип](../../../ado/reference/ado-api/type-property-ado.md) . Для поля, использующего тип данных фиксированной длины, возвращаемое значение — это размер типа данных в байтах. Для поля, использующего тип данных переменной длины, это одно из следующих:  
  
1.  Максимальная длина поля в символах (для **адварчар** и **адварвчар**) или в байтах (для **адварбинари** и **адварнумерик**), если поле имеет определенную длину. Например, поле **адварчар (5)** имеет максимальную длину 5.  
  
2.  Максимальная длина типа данных в символах (для **адчар** и **адвчар**) или в байтах (для **адбинари** и **аднумерик**), если поле не имеет определенной длины.  
  
3.  ~ 0 (побитовое значение не равно 0; все биты установлены в 1), если ни поле, ни тип данных не имеют определенной максимальной длины.  
  
4.  Для типов данных, длина которых не превышает длину, для этого параметра задано значение ~ 0 (битовая, а не 0, все биты установлены в 1).  
  
## <a name="remarks"></a>Замечания  
 Используйте свойство **DefinedSize** , чтобы определить емкость данных для объекта **поля** .  
  
 Свойства **DefinedSize** и [ActualSize](../../../ado/reference/ado-api/actualsize-property-ado.md) различаются. Например, рассмотрим объект **field** с объявленным типом **адварчар** и значением свойства **DefinedSize** 50, содержащим один символ. Возвращаемое значение свойства **ActualSize** — это длина в байтах одного символа.  
  
## <a name="applies-to"></a>Применение  
 [Объект Field](../../../ado/reference/ado-api/field-object.md)  
  
## <a name="see-also"></a>См. также:  
 [Примеры свойств ActualSize и DefinedSize (Visual Basic)](../../../ado/reference/ado-api/actualsize-and-definedsize-properties-example-vb.md)   
 [Пример свойств ActualSize и DefinedSize (Visual c++)](../../../ado/reference/ado-api/actualsize-and-definedsize-properties-example-vc.md)   
 [Свойство ActualSize (ADO)](../../../ado/reference/ado-api/actualsize-property-ado.md)
