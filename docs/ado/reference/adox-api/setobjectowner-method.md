---
description: Метод SetObjectOwner
title: Метод SetObjectOwner | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _Catalog::SetObjectOwner
- _Catalog::raw_SetObjectOwner
helpviewer_keywords:
- SetObjectOwner method [ADOX]
ms.assetid: e5170a37-9d6e-43db-bfb6-9b6631fa3048
author: rothja
ms.author: jroth
ms.openlocfilehash: 2d75966ce8d5c1f9fddea9c09ff254eca9106e62
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100053809"
---
# <a name="setobjectowner-method"></a>Метод SetObjectOwner
Указывает владельца объекта в [каталоге](./catalog-object-adox.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Catalog.SetObjectOwner ObjectName, ObjectType, OwnerName [,ObjectTypeId]  
```  
  
#### <a name="parameters"></a>Параметры  
 *ObjectName*  
 **Строковое** значение, указывающее имя объекта, для которого необходимо указать владельца.  
  
 *ObjectType*  
 Значение типа **Long** , которое может быть одной из констант [обжекттипинум](./objecttypeenum.md) , которое указывает тип владельца.  
  
 *OwnerName*  
 **Строковое** значение, указывающее [имя](./name-property-adox.md) [пользователя](./user-object-adox.md) или [группы](./group-object-adox.md) для владельца объекта.  
  
 *обжекттипеид*  
 Необязательный элемент. Значение **типа Variant** , указывающее идентификатор GUID для типа объекта поставщика, который не определен спецификацией OLE DB. Этот параметр является обязательным, если для *ObjectType* задано значение **адпермобжпровидерспеЦифик**. в противном случае он не используется.  
  
## <a name="remarks"></a>Remarks  
 Если поставщик не поддерживает указание владельцев объектов, возникнет ошибка.  
  
## <a name="applies-to"></a>Применение  
 [Объект Catalog (ADOX)](./catalog-object-adox.md)  
  
## <a name="see-also"></a>См. также:  
 [Примеры методов примеры методов getobjectowner и SetObjectOwner (Visual Basic)](./getobjectowner-and-setobjectowner-methods-example-vb.md)   
 [Метод GetObjectOwner (ADOX)](./getobjectowner-method-adox.md)