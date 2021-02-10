---
description: Коллекция Users (ADOX)
title: Коллекция пользователей (ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Group::Users
- Users
- Catalog::Users
helpviewer_keywords:
- Users collection [ADOX]
ms.assetid: 0a30fa74-6f10-4410-bd70-882e7c43cd46
author: rothja
ms.author: jroth
ms.openlocfilehash: 781f9eb90c621cf8daf4afb0cdf8dc4f1f7b47b4
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100049674"
---
# <a name="users-collection-adox"></a>Коллекция Users (ADOX)
Содержит все сохраненные [пользовательские](./user-object-adox.md) объекты [каталога](./catalog-object-adox.md) или [группы](./group-object-adox.md).  
  
## <a name="remarks"></a>Remarks  
 Коллекция **пользователей** [каталога](./catalog-object-adox.md) представляет всех пользователей каталога. Коллекция **пользователей** для [группы](./group-object-adox.md) представляет только тех пользователей, которые имеют членство в определенной группе.  
  
 Метод [append](./append-method-adox-users.md) для коллекции **пользователей** уникален для ADOX. Вы можете выбрать один из следующих вариантов.  
  
-   Добавьте нового пользователя в коллекцию с помощью метода **append** .  
  
 Остальные свойства и методы являются стандартными для коллекций ADO. Вы можете выбрать один из следующих вариантов.  
  
-   Доступ к пользователю в коллекции со свойством [Item](../ado-api/item-property-ado.md) .  
  
-   Возвращает число пользователей, содержащихся в коллекции, с помощью свойства [Count](../ado-api/count-property-ado.md) .  
  
-   Удалите пользователя из коллекции с помощью метода [Delete](./delete-method-adox-collections.md) .  
  
-   Обновите объекты в коллекции, чтобы отразить схему текущей базы данных методом [Refresh](../ado-api/refresh-method-ado.md) .  
  
> [!NOTE]
>  Перед добавлением объекта **пользователя** в коллекцию **Users** объекта **Group** объект **пользователя** с тем же [именем](./name-property-adox.md) , что и у добавляемого, должен уже существовать в коллекции **пользователей** **каталога**.  
  
 Этот раздел содержит следующий раздел.  
  
-   [Свойства, методы и события коллекции Users](./users-collection-properties-methods-and-events.md)  
  
## <a name="see-also"></a>См. также:  
 [Примеры методов SetPermissions и Methods (Visual Basic)](./getpermissions-and-setpermissions-methods-example-vb.md)   
 [Объект каталога (ADOX)](./catalog-object-adox.md)   
 [Объект User (ADOX)](./user-object-adox.md)