---
description: Метод SetPermissions (ADOX)
title: Метод SetPermissions (ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- User25::SetPermissions
- User25::raw_SetPermissions
- _Group25::SetPermissions
- _Group25::raw_SetPermissions
helpviewer_keywords:
- SetPermissions method [ADOX]
ms.assetid: b7f925d7-b05c-4376-bb49-f8d2c17b8b24
author: rothja
ms.author: jroth
ms.openlocfilehash: 84c7e3fd8ff31a83e27f4e66036ad8e90d2031f3
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100049754"
---
# <a name="setpermissions-method-adox"></a>Метод SetPermissions (ADOX)
Задает разрешения для [группы](./group-object-adox.md) или [пользователя](./user-object-adox.md) на объекте.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
GroupOrUser.SetPermissions Name, ObjectType, Action, Rights [, Inherit] [, ObjectTypeId]  
```  
  
#### <a name="parameters"></a>Параметры  
 *Имя*  
 **Строковое** значение, указывающее имя объекта, для которого задаются разрешения.  
  
 *ObjectType*  
 Значение типа **Long** , которое может быть одной из констант [обжекттипинум](./objecttypeenum.md) , указывающее тип объекта, для которого нужно получить разрешения.  
  
 *Действие*  
 Значение типа **Long** , которое может быть одной из констант [актионенум](./actionenum.md) , которое указывает тип действия, выполняемого при установке разрешений.  
  
 *Права*  
 **Длинное** значение, которое может быть битовой маской одной или нескольких констант [ригхтсенум](./rightsenum.md) , указывающих права на установку.  
  
 *Следующих*  
 Необязательный элемент. Значение **типа Long** , которое может быть одной из констант [инхериттипинум](./inherittypeenum.md) , которое указывает, как объекты будут наследовать эти разрешения. Значение по умолчанию — **адинхеритноне**.  
  
 *обжекттипеид*  
 Необязательный элемент. Значение **типа Variant** , указывающее идентификатор GUID для типа объекта поставщика, который не определен спецификацией OLE DB. Этот параметр является обязательным, если для *ObjectType* задано значение **адпермобжпровидерспеЦифик**. в противном случае он не используется.  
  
## <a name="remarks"></a>Remarks  
 Если поставщик не поддерживает установку прав доступа для групп или пользователей, возникнет ошибка.  
  
> [!NOTE]
>  При вызове **SetPermissions** Установка действий в **адакцессревоке** переопределяет все параметры параметра *Rights* . Не устанавливайте *действия* в **адакцессревоке** , если вы хотите, чтобы права, указанные в параметре *Rights* , вступили в силу.  
  
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
 [Метод PermissionSet (ADOX)](./getpermissions-method-adox.md)   
 [Свойство Name (ADOX)](./name-property-adox.md)