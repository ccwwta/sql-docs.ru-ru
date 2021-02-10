---
description: Свойство Number (ADO)
title: Свойство Number (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Error::Number
- Error::GetNumber
- Error::get_Number
helpviewer_keywords:
- number property [ADO]
ms.assetid: f92323c5-dd11-4a63-a505-d9014a0f067f
author: rothja
ms.author: jroth
ms.openlocfilehash: c39192c6158dfdd180c6f3235668157b9750e1e0
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100041564"
---
# <a name="number-property-ado"></a>Свойство Number (ADO)
Указывает число, которое однозначно определяет объект [ошибки](./error-object.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение **типа Long** , которое может соответствовать одной из констант [еррорвалуинум](./errorvalueenum.md) .  
  
## <a name="remarks"></a>Remarks  
 Чтобы определить, какая ошибка возникла, используйте свойство **Number** . Значение свойства является уникальным числом, которое соответствует условию ошибки.  
  
 Коллекция [Errors](./errors-collection-ado.md) ВОЗВРАЩАЕТ значение HRESULT в шестнадцатеричном формате (например, 0x80004005) или длинном значении (например, 2147467259). Эти значения HRESULT могут быть вызваны базовыми компонентами, такими как OLE DB или даже самим OLE. Дополнительные сведения об этих номерах см. в разделе [ошибки (OLE DB)](/previous-versions/windows/desktop/ms724533(v=vs.85)) в [справочнике по программисту OLE DB](/previous-versions/windows/desktop/ms713643(v=vs.85))*.*  
  
## <a name="applies-to"></a>Применение  
 [Объект Error](./error-object.md)  
  
## <a name="see-also"></a>См. также:  
 [Примеры свойств Description, HelpContext, HelpFile, NativeError, Number, Source и SQLState (Visual Basic)](./description-helpcontext-helpfile-nativeerror-number-source-example-vb.md)   
 [Примеры свойств Description, HelpContext, HelpFile, NativeError, Number, Source и SQLState (Visual c++)](./description-helpcontext-helpfile-nativeerror-number-source-example-vc.md)   
 [Свойство Description](./description-property.md)   
 [Свойства HelpContext, HelpFile](./helpcontext-helpfile-properties.md)   
 [Свойство Source (объект Error ADO)](./source-property-ado-error.md)