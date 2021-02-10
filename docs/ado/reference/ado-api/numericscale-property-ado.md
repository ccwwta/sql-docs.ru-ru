---
description: Свойство NumericScale (ADO)
title: Свойство NumericScale (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _Parameter::NumericScale
- Field20::NumericScale
helpviewer_keywords:
- NumericScale property [ADO]
ms.assetid: 29a02992-64be-4fcd-be13-445cba205893
author: rothja
ms.author: jroth
ms.openlocfilehash: 265b5a1c0e435bb9eef9fedd5b28f5db2e4a7258
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100041494"
---
# <a name="numericscale-property-ado"></a>Свойство NumericScale (ADO)
Указывает масштаб числовых значений в объекте [параметра](./parameter-object.md) или [поля](./field-object.md) .  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает или возвращает значение **типа Byte** , указывающее количество десятичных разрядов, к которым будут разрешены числовые значения.  
  
## <a name="remarks"></a>Remarks  
 Используйте свойство **NumericScale** , чтобы определить, сколько цифр справа от десятичной запятой будет использоваться для представления значений числового **параметра** или объекта **поля** .  
  
 Для объектов **параметров** свойство **NumericScale** доступно для чтения и записи.  
  
 Для объекта **field** **NumericScale** обычно доступен только для чтения. Однако для новых объектов **field** , добавленных к коллекции [Fields](./fields-collection-ado.md) [записи](./record-object-ado.md), **NumericScale** доступен только для чтения и записи только после того, как было указано свойство [value](./value-property-ado.md) для **поля** и поставщик данных успешно добавил новое **поле** , вызвав метод [Update](./update-method.md) коллекции [Fields](./fields-collection-ado.md) .  
  
## <a name="applies-to"></a>Применение  

:::row:::
    :::column:::
        [Объект Field](./field-object.md)  
    :::column-end:::
    :::column:::
        [Объект Parameter](./parameter-object.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>См. также:  
 [Пример свойств NumericScale и Precision (Visual Basic)](./numericscale-and-precision-properties-example-vb.md)   
 [Пример свойств NumericScale и Precision (Visual c++)](./numericscale-and-precision-properties-example-vc.md)   
 [Свойство Precision (ADO)](./precision-property-ado.md)