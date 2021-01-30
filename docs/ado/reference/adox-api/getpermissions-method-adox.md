---
description: Метод GetPermissions (ADOX)
title: Метод PermissionSet (ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _User25::GetPermissions
- _Group25::raw_GetPermissions
- _Group25::GetPermissions
- _User25::raw_GetPermissions
helpviewer_keywords:
- GetPermissions method [ADOX]
ms.assetid: df201c1f-c76a-465d-98f0-83b7fc36e6e3
author: rothja
ms.author: jroth
ms.openlocfilehash: 4c4d96176e4bdad70cbd5c09a59adcade6f99f81
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99169386"
---
# <a name="getpermissions-method-adox"></a>Метод GetPermissions (ADOX)
Возвращает разрешения для [группы](./group-object-adox.md) или [пользователя](./user-object-adox.md) в контейнере объекта или объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
ReturnValue=GroupOrUser.GetPermissions(Name, ObjectType    [,ObjectTypeId])  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение **типа Long** , указывающее битовую маску, содержащую разрешения, которые группа или пользователь имеет на объекте. Это значение может быть одной или несколькими константами [ригхтсенум](./rightsenum.md) .  
  
#### <a name="parameters"></a>Параметры  
 *Имя*  
 Значение **типа Variant** , указывающее имя объекта, для которого задаются разрешения. Задайте для *Name* значение null, если требуется получить разрешения для контейнера объектов.  
  
 *ObjectType*  
 Значение типа **Long** , которое может быть одной из констант [обжекттипинум](./objecttypeenum.md) , указывающее тип объекта, для которого нужно получить разрешения.  
  
 *обжекттипеид*  
 Необязательный параметр. Значение **типа Variant** , указывающее идентификатор GUID для типа объекта поставщика, не определенного спецификацией OLE DB. Этот параметр является обязательным, если для *ObjectType* задано значение **адпермобжпровидерспеЦифик**. в противном случае он не используется.  
  
## <a name="applies-to"></a>Применение  

:::row:::
    :::column:::
        [Объект Group (ADOX)](./group-object-adox.md)  
    :::column-end:::
    :::column:::
        [Объект User (ADOX)](./user-object-adox.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>См. также:  
 [Примеры методов SetPermissions и Methods (Visual Basic)](./getpermissions-and-setpermissions-methods-example-vb.md)   
 [Свойство Name (ADOX)](./name-property-adox.md)   
 [Метод SetPermissions (ADOX)](./setpermissions-method-adox.md)