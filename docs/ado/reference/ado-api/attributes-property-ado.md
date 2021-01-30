---
description: Свойство Attributes (ADO)
title: Свойство Attributes (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Connection15::Attributes
- Field20::Attributes
- _Parameter::Attributes
helpviewer_keywords:
- Attributes property [ADO]
ms.assetid: acc15d40-68a6-4ba9-85bd-12d331aecaa6
author: rothja
ms.author: jroth
ms.openlocfilehash: 72cbd650b2ab3c66231383e89b048bb03c42b6f5
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99164808"
---
# <a name="attributes-property-ado"></a>Свойство Attributes (ADO)
Указывает одну или несколько характеристик объекта.  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает или возвращает значение **типа Long** .  
  
 Для объекта [соединения](./connection-object-ado.md) свойство **Attributes** доступно для чтения и записи, а его значение может быть суммой одного или нескольких значений [ксактаттрибутинум](./xactattributeenum.md) . Значение по умолчанию равно нулю (0).  
  
 Для объекта [параметра](./parameter-object.md) свойство **Attributes** доступно для чтения и записи, а его значение может быть суммой любого одного или нескольких значений [параметераттрибутесенум](./parameterattributesenum.md) . Значение по умолчанию — **адпарамсигнед**.  
  
 Для объекта [field](./field-object.md) свойство **Attributes** может быть суммой одного или нескольких значений [фиелдаттрибутинум](./fieldattributeenum.md) . Обычно он доступен только для чтения. Однако для новых объектов **field** , добавленных к коллекции [Fields](./fields-collection-ado.md) [записи](./record-object-ado.md), **атрибуты** доступны только для чтения и записи только после того, как было указано свойство [value](./value-property-ado.md) для **поля** и новое **поле** было успешно добавлено поставщиком данных путем вызова метода [Update](./update-method.md) коллекции **Fields** .  
  
 Для объекта [Property](./property-object-ado.md) свойство **Attributes** доступно только для чтения, а его значение может быть суммой любого одного или нескольких значений [пропертяттрибутесенум](./propertyattributesenum.md) .  
  
## <a name="remarks"></a>Замечания  
 Свойство **Attributes** используется для задания или возвращения характеристик объектов **соединения** , объектов **параметров** , объектов **полей** или объектов **свойств** .  
  
 При задании нескольких атрибутов можно суммировать соответствующие константы. Если задать для свойства значение Sum, включая несовместимые константы, возникает ошибка.  
  
> [!NOTE]
>  **Использование удаленной службы данных** Это свойство недоступно для объекта **подключения** на стороне клиента.  
  
## <a name="applies-to"></a>Применение  

:::row:::
    :::column:::
        [Объект Connection (ADO)](./connection-object-ado.md)  
        [Объект Field](./field-object.md)  
    :::column-end:::
    :::column:::
        [Объект Parameter](./parameter-object.md)  
        [Объект Property (ADO)](./property-object-ado.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>См. также:  
 [Пример атрибутов и свойств имени (Visual Basic)](./attributes-and-name-properties-example-vb.md)   
 [Пример атрибутов и свойств имени (Visual c++)](./attributes-and-name-properties-example-vc.md)   
 [Метод AppendChunk (ADO)](./appendchunk-method-ado.md)   
 [Методы примеры BeginTrans, CommitTrans и RollbackTrans (ADO)](./begintrans-committrans-and-rollbacktrans-methods-ado.md)   
 [Метод GetChunk (ADO)](./getchunk-method-ado.md)