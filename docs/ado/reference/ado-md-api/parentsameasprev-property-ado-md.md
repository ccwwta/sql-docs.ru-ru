---
description: Свойство ParentSameAsPrev (многомерные объекты ADO)
title: Свойство Парентсамеаспрев (объекты данных ActiveX (MD)) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- ParentSameAsPrev
- Member::ParentSameAsPrev
helpviewer_keywords:
- ParentSameAsPrev property [ADO MD]
ms.assetid: 510842e0-e8dc-4b33-9517-bd1c6df0cf3c
author: rothja
ms.author: jroth
ms.openlocfilehash: 99db74fbed7f5bcf797f88a44e1c5eb09a5a3eac
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100050945"
---
# <a name="parentsameasprev-property-ado-md"></a>Свойство ParentSameAsPrev (многомерные объекты ADO)
Указывает, совпадает ли родительский элемент данного [элемента](./member-object-ado-md.md) позиционирования с родительским элементом непосредственно предыдущего элемента.  
  
## <a name="return-values"></a>Возвращаемые значения  
 Возвращает **логическое** значение и доступно только для чтения.  
  
## <a name="remarks"></a>Remarks  
 Это свойство поддерживается только для объектов [member](./member-object-ado-md.md) , принадлежащих объекту- [положению](./position-object-ado-md.md) . Ошибка возникает, когда на это свойство ссылаются объекты- **члены** , принадлежащие объекту [уровня](./level-object-ado-md.md) .  
  
## <a name="applies-to"></a>Применение  
 [Объект Member (многомерные объекты ADO)](./member-object-ado-md.md)  
  
## <a name="see-also"></a>См. также:  
 [Свойство DrilledDown (многомерные объекты ADO)](./drilleddown-property-ado-md.md)