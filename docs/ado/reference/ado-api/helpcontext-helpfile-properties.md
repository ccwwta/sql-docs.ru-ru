---
description: Свойства HelpContext и HelpFile
title: HelpContext, свойства HelpFile | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Error::GetHelpContext
- Error::GetHelpFile
- Error::get_HelpFile
- Error::get_HelpContext
- Error::HelpContext
- Error::HelpFile
helpviewer_keywords:
- HelpContext property [ADO]
- HelpFile property [ADO]
ms.assetid: 2b9ef441-993c-44d4-8f87-fac0979dac1d
author: rothja
ms.author: jroth
ms.openlocfilehash: 355f3047a31e82d034cfe23b2d1c069d07a7bbab
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99170949"
---
# <a name="helpcontext-helpfile-properties"></a>Свойства HelpContext и HelpFile
Указывает файл справки и раздел, связанный с объектом [Error](./error-object.md) .  
  
## <a name="return-values"></a>Возвращаемые значения  
  
-   **Хелпконтекстид** Возвращает идентификатор контекста в виде **длинного** значения для раздела в файле справки.  
  
-   **HelpFile** Возвращает **строковое** значение, результатом которого является полностью разрешенный путь к файлу справки.  
  
## <a name="remarks"></a>Замечания  
 Если в свойстве **HelpFile** указан файл справки, свойство **HelpContext** используется для автоматического вывода справочного раздела, который он идентифицирует. Если соответствующий раздел справки недоступен, свойство **HelpContext** возвращает нуль, а свойство **HelpFile** возвращает строку нулевой длины ("").  
  
## <a name="applies-to"></a>Применение  
 [Объект Error](./error-object.md)  
  
## <a name="see-also"></a>См. также:  
 [Примеры свойств Description, HelpContext, HelpFile, NativeError, Number, Source и SQLState (Visual Basic)](./description-helpcontext-helpfile-nativeerror-number-source-example-vb.md)   
 [Примеры свойств Description, HelpContext, HelpFile, NativeError, Number, Source и SQLState (Visual c++)](./description-helpcontext-helpfile-nativeerror-number-source-example-vc.md)   
 [Свойство Description](./description-property.md)   
 [Свойство Number (ADO)](./number-property-ado.md)   
 [Свойство Source (объект Error ADO)](./source-property-ado-error.md)