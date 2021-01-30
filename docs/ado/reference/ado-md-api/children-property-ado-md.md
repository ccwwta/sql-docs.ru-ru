---
description: Свойство Children (многомерные объекты ADO)
title: Свойство Children (объекты данных ActiveX (MD)) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Member::Children
- Children
helpviewer_keywords:
- Children property [ADO MD]
ms.assetid: 61d36468-1ccd-467a-9cb5-17d0bfacc766
author: rothja
ms.author: jroth
ms.openlocfilehash: 81cbaddf1db2017384392e20b249b9c1beb3ccd0
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99169915"
---
# <a name="children-property-ado-md"></a>Свойство Children (многомерные объекты ADO)
Возвращает коллекцию [Members](./members-collection-ado-md.md) , для которой текущий [элемент](./member-object-ado-md.md) является родительским в иерархии.  
  
## <a name="return-values"></a>Возвращаемые значения  
 Возвращает коллекцию **Members** и доступна только для чтения.  
  
## <a name="remarks"></a>Замечания  
 Свойство **Children** содержит коллекцию **Members** , для которой текущий **элемент** является иерархическим родителем. Объекты **элементов** конечного уровня не имеют дочерних элементов в коллекции **Members** . Это свойство поддерживается только для объектов- **членов** , принадлежащих объекту [уровня](./level-object-ado-md.md) . Ошибка возникает, когда на это свойство ссылаются объекты- **члены** , принадлежащие объекту- [положению](./position-object-ado-md.md) .  
  
## <a name="applies-to"></a>Применение  
 [Объект Member (многомерные объекты ADO)](./member-object-ado-md.md)  
  
## <a name="see-also"></a>См. также:  
 [Свойство ChildCount (многомерные объекты ADO)](./childcount-property-ado-md.md)