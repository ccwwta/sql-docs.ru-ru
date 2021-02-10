---
description: Свойство Type (ADO)
title: Свойство Type (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _Parameter::Type
- Field20::Type
helpviewer_keywords:
- Type property [ADO]
ms.assetid: 8a4c079f-9f4f-4545-801d-85983b8db71e
author: rothja
ms.author: jroth
ms.openlocfilehash: feb964fbc6cdd59be000e82c4a58b359cfc23d57
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100056439"
---
# <a name="type-property-ado"></a>Свойство Type (ADO)
Указывает операционный тип или тип данных для [параметра](./parameter-object.md), [поля](./field-object.md)или объекта [Свойства](./property-object-ado.md) .  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает или возвращает значение [дататипинум](./datatypeenum.md) .  
  
## <a name="remarks"></a>Remarks  
 Для объектов **параметров** свойство **Type** доступно для чтения и записи. Для новых **объектов Field** , добавленных к коллекции [Fields](./fields-collection-ado.md) [записи](./record-object-ado.md), **тип** доступен только для чтения и записи только после того, как было указано свойство [value](./value-property-ado.md) для **поля** и поставщик данных успешно добавил новое **поле** , вызвав метод [Update](./update-method.md) коллекции **Fields** .  
  
 Для всех остальных объектов свойство **Type** доступно только для чтения.  
  
## <a name="applies-to"></a>Применение  

:::row:::
    :::column:::
        [Объект Field](./field-object.md)  
    :::column-end:::
    :::column:::
        [Объект Parameter](./parameter-object.md)  
    :::column-end:::
    :::column:::
        [Объект Property (ADO)](./property-object-ado.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>См. также:  
 [Пример свойства Type (Field) (VB)](./type-property-example-field-vb.md)   
 [Пример свойства Type (Property) (VC + +)](./type-property-example-property-vc.md)   
 [Свойство RecordType (ADO)](./recordtype-property-ado.md)   
 [Свойство Type (объект Stream ADO)](./type-property-ado-stream.md)