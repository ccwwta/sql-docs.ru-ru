---
description: Свойство EOS
title: EOS, свойство | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- EOS
- Stream::EOS
helpviewer_keywords:
- EOS property
ms.assetid: 57e08c5f-f3ed-4ecd-8c66-50b83b1031d1
author: rothja
ms.author: jroth
ms.openlocfilehash: 45268bfba7669f3c202cec9bc652424981e1234e
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100025128"
---
# <a name="eos-property"></a>Свойство EOS
Указывает, находится ли текущая координата в конце [потока](../../../ado/reference/ado-api/stream-object-ado.md).  
  
## <a name="return-values"></a>Возвращаемые значения  
 Возвращает **логическое** значение, указывающее, находится ли текущая позиции в конце потока. **EOS** возвращает **значение true** , если в потоке больше нет байтов; Он возвращает **значение false** , если после текущей позицией находится больше байтов.  
  
 Чтобы задать окончание расположения потока, используйте метод [сетеос](../../../ado/reference/ado-api/seteos-method.md) . Чтобы определить текущую точку, используйте свойство " [позиционирование](../../../ado/reference/ado-api/position-property-ado.md) ".  
  
## <a name="applies-to"></a>Применение  
 [Объект Stream (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример свойств EOS и LineSeparator и метод Скиплине (Visual Basic)](../../../ado/reference/ado-api/eos-and-lineseparator-properties-and-skipline-method-example-vb.md)   
 [Объект Stream (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)
