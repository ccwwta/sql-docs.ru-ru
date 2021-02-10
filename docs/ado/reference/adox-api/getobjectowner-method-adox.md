---
description: Метод GetObjectOwner (ADOX)
title: Метод примеры методов getobjectowner (ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _Catalog::raw_GetObjectOwner
- _Catalog::GetObjectOwner
helpviewer_keywords:
- GetObjectOwner method [ADOX]
ms.assetid: 8965adf0-9075-4125-8142-73eb700029c3
author: rothja
ms.author: jroth
ms.openlocfilehash: 8657feb52c09f8d4ef04517985201d9a2aa8f80c
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100054209"
---
# <a name="getobjectowner-method-adox"></a>Метод GetObjectOwner (ADOX)
Возвращает владельца объекта в [каталоге](./catalog-object-adox.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Owner = Catalog.GetObjectOwner(ObjectName, ObjectType [,ObjectTypeId])  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает **строковое** значение, указывающее [имя](./name-property-adox.md) [пользователя](./user-object-adox.md) или [группы](./group-object-adox.md) , которым принадлежит объект.  
  
#### <a name="parameters"></a>Параметры  
 *ObjectName*  
 **Строковое** значение, указывающее имя объекта, для которого возвращается владелец.  
  
 *ObjectType*  
 Значение типа **Long** , которое может быть одной из констант [обжекттипинум](./objecttypeenum.md) , указывающее тип объекта, для которого необходимо получить владельца.  
  
 *обжекттипеид*  
 Необязательный элемент. Значение **типа Variant** , указывающее идентификатор GUID для типа объекта поставщика, не определенного спецификацией OLE DB. Этот параметр является обязательным, если для *ObjectType* задано значение **адпермобжпровидерспеЦифик**. в противном случае он не используется.  
  
## <a name="remarks"></a>Remarks  
 Если поставщик не поддерживает возврат владельцев объектов, возникнет ошибка.  
  
## <a name="applies-to"></a>Применение  
 [Объект Catalog (ADOX)](./catalog-object-adox.md)  
  
## <a name="see-also"></a>См. также:  
 [Примеры методов примеры методов getobjectowner и SetObjectOwner (Visual Basic)](./getobjectowner-and-setobjectowner-methods-example-vb.md)   
 [Метод SetObjectOwner](./setobjectowner-method.md)