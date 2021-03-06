---
description: Свойство FormattedValue (многомерные объекты ADO)
title: Свойство FormattedValue (объекты данных ActiveX (MD)) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Cell::FormattedValue
- FormattedValue
helpviewer_keywords:
- FormattedValue property [ADO MD]
ms.assetid: 5c06451e-06ec-4da6-9a87-2d043469248a
author: rothja
ms.author: jroth
ms.openlocfilehash: aba336cff29c02f1468ed1763d005990cc465adb
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100054760"
---
# <a name="formattedvalue-property-ado-md"></a>Свойство FormattedValue (многомерные объекты ADO)
Указывает отформатированное отображение значения [ячейки](./cell-object-ado-md.md) .  
  
## <a name="return-values"></a>Возвращаемые значения  
 Возвращает **строку** и доступна только для чтения.  
  
## <a name="remarks"></a>Remarks  
 Используйте свойство **FormattedValue** для получения форматированного отображаемого значения свойства [value](./value-property-ado-md.md) объекта [ячейки](./cell-object-ado-md.md) . Например, если значение ячейки 1056,87, а это значение представляло собой сумму в долларах, **FormattedValue** будет $1 056,87.  
  
## <a name="applies-to"></a>Применение  
 [Объект Cell (многомерные объекты ADO)](./cell-object-ado-md.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример набора ячеек (Visual Basic)](./cellset-example-vb.md)   
 [Свойство Value (многомерные объекты ADO)](./value-property-ado-md.md)