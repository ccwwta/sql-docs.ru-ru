---
description: Свойство NativeError (ADO)
title: Свойство NativeError (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Error::GetNativeError
- Error::get_NativeError
- Error::NativeError
helpviewer_keywords:
- NativeError property [ADO]
ms.assetid: b9b47e57-18a4-4186-aef5-5bd18d7b1d74
author: rothja
ms.author: jroth
ms.openlocfilehash: 10ed79bf5629ce6439362ce1e80226444928a16b
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100041594"
---
# <a name="nativeerror-property-ado"></a>Свойство NativeError (ADO)
Указывает код ошибки конкретного поставщика для данного объекта [ошибки](./error-object.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение **типа Long** , указывающее код ошибки.  
  
## <a name="remarks"></a>Remarks  
 Используйте свойство **NativeError** , чтобы получить сведения об ошибке конкретной базы данных для конкретного объекта **ошибки** . Например, при использовании поставщика Microsoft ODBC для OLE DB с базой данных Microsoft SQL Server, машинные коды ошибок, происходящие из SQL Server, проходят через ODBC и поставщик ODBC в свойство ADO **NativeError** .  
  
## <a name="applies-to"></a>Применение  
 [Объект Error](./error-object.md)  
  
## <a name="see-also"></a>См. также:  
 [Примеры свойств Description, HelpContext, HelpFile, NativeError, Number, Source и SQLState (Visual Basic)](./description-helpcontext-helpfile-nativeerror-number-source-example-vb.md)   
 [Примеры свойств Description, HelpContext, HelpFile, NativeError, Number, Source и SQLState (Visual c++)](./description-helpcontext-helpfile-nativeerror-number-source-example-vc.md)