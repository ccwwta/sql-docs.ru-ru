---
description: Свойство Description (многомерные объекты ADO)
title: Свойство Description (объекты данных ActiveX (MD)) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Member::Description
- Level::Description
- CubeDef::Description
- Hierarchy::Description
- Description
- Dimension::Description
helpviewer_keywords:
- Description property [ADO MD]
ms.assetid: 6d626d35-0bf3-4f24-9934-ad9c9c91273a
author: rothja
ms.author: jroth
ms.openlocfilehash: 4fbb1ff444c4d5b2cbf233ec2999411ab11ddfd9
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100051165"
---
# <a name="description-property-ado-md"></a>Свойство Description (многомерные объекты ADO)
Возвращает текстовое описание текущего объекта.  
  
## <a name="return-values"></a>Возвращаемые значения  
 Возвращает **строку** и доступна только для чтения.  
  
## <a name="remarks"></a>Remarks  
 Для объектов [member](./member-object-ado-md.md) **Описание** применяется только к элементам Measure и формуле. **Описание** возвращает пустую строку ("") для всех других типов элементов. Дополнительные сведения о различных типах членов см. в описании свойства [Type](./type-property-ado-md.md) .  
  
 Это свойство поддерживается только для объектов- **членов** , принадлежащих объекту [уровня](./level-object-ado-md.md) . Ошибка возникает, когда на это свойство ссылаются объекты- **члены** , принадлежащие объекту- [положению](./position-object-ado-md.md) .  
  
## <a name="applies-to"></a>Применение  

:::row:::
    :::column:::
        [Объект CubeDef (многомерные объекты ADO)](./cubedef-object-ado-md.md)  
        [Объект Dimension (многомерные объекты ADO)](./dimension-object-ado-md.md)  
    :::column-end:::
    :::column:::
        [Объект Hierarchy (многомерные объекты ADO)](./hierarchy-object-ado-md.md)  
        [Объект Level (многомерные объекты ADO)](./level-object-ado-md.md)  
    :::column-end:::
    :::column:::
        [Объект Member (многомерные объекты ADO)](./member-object-ado-md.md)  
    :::column-end:::
:::row-end:::