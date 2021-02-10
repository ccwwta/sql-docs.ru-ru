---
title: Свойство Description | Документация Майкрософт
description: Сведения о свойстве Description объекта Error в ADO, возвращающем строковое значение, содержащее описание ошибки.
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Error::Description
- Error::GetDescription
- Error::get_Description
helpviewer_keywords:
- Description property
ms.assetid: 4b5d6790-6c29-42aa-bf78-d9cfb8ad7965
author: rothja
ms.author: jroth
ms.openlocfilehash: 7181bffdad12291c08bf4fb5c6a00b4b1b2a6cc5
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100034314"
---
# <a name="description-property"></a>Свойство Description
Описывает объект [Error](../../../ado/reference/ado-api/error-object.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает **строковое** значение, содержащее описание ошибки.  
  
## <a name="remarks"></a>Remarks  
 Используйте свойство **Description** для получения краткого описания ошибки. Отобразить это свойство, чтобы предупредить пользователя об ошибке, которую нельзя или не требуется обменять. Строка будет поступать из ADO или поставщика.  
  
 Поставщики несут ответственность за передачу конкретного текста ошибок в ADO. ADO добавляет объект [Error](../../../ado/reference/ado-api/error-object.md) в коллекцию **Errors** для каждой ошибки поставщика или предупреждения, которое она получает. Перечислите коллекцию **Errors** , чтобы отслеживать ошибки, передаваемые поставщиком.  
  
## <a name="applies-to"></a>Применение  
 [Объект Error](../../../ado/reference/ado-api/error-object.md)  
  
## <a name="see-also"></a>См. также:  
 [Примеры свойств Description, HelpContext, HelpFile, NativeError, Number, Source и SQLState (Visual Basic)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vb.md)   
 [Примеры свойств Description, HelpContext, HelpFile, NativeError, Number, Source и SQLState (Visual c++)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vc.md)   
 [Свойства HelpContext, HelpFile](../../../ado/reference/ado-api/helpcontext-helpfile-properties.md)   
 [Свойство Number (ADO)](../../../ado/reference/ado-api/number-property-ado.md)   
 [Свойство Source (объект Error ADO)](../../../ado/reference/ado-api/source-property-ado-error.md)
