---
description: Свойство PageCount (ADO)
title: Свойство PageCount (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Recordset15::PageCount
helpviewer_keywords:
- PageCount property [ADO]
ms.assetid: b601b56c-0ac4-44ee-bc91-c3d2d104f00a
author: rothja
ms.author: jroth
ms.openlocfilehash: 828a0f9d872ab1040700941d85980e0b5deecf98
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100041234"
---
# <a name="pagecount-property-ado"></a>Свойство PageCount (ADO)
Указывает, сколько страниц данных содержит объект [Recordset](./recordset-object-ado.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение **типа Long** , указывающее количество страниц в **наборе записей**.  
  
## <a name="remarks"></a>Remarks  
 Используйте свойство **PageCount** , чтобы определить, сколько страниц данных находится в объекте **Recordset** . *Страницы* — это группы записей, размер которых равен значению свойства [pageSize](./pagesize-property-ado.md) . Даже если последняя страница является неполной, так как число записей меньше, чем значение **pageSize** , оно считается дополнительной страницей в значении **PageCount** . Если объект **Recordset** не поддерживает это свойство, значение будет равно-1, чтобы указать, что **PageCount** недетерминирована.  
  
 Дополнительные сведения о функциях страницы см. в разделе Свойства **pageSize** и [примеры absolutepage](./absolutepage-property-ado.md) .  
  
## <a name="applies-to"></a>Применение  
 [Объект Recordset (ADO)](./recordset-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Примеры свойств примеры absolutepage, PageCount и PageSize (Visual Basic)](./absolutepage-pagecount-and-pagesize-properties-example-vb.md)   
 [Пример свойств примеры absolutepage, PageCount и PageSize (Visual c++)](./absolutepage-pagecount-and-pagesize-properties-example-vc.md)   
 [Свойство примеры absolutepage (ADO)](./absolutepage-property-ado.md)   
 [Свойство PageSize (ADO)](./pagesize-property-ado.md)   
 [Свойство RecordCount (ADO)](./recordcount-property-ado.md)