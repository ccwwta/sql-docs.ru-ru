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
ms.openlocfilehash: 84fffacf0795d60808e172185251f3135bd0d7d4
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99169122"
---
# <a name="users-collection-adox"></a>Коллекция Users (ADOX)
Содержит все сохраненные [пользовательские](./user-object-adox.md) объекты [каталога](./catalog-object-adox.md) или [группы](./group-object-adox.md).  
  
## <a name="remarks"></a>Замечания  
 Коллекция **пользователей** [каталога](./catalog-object-adox.md) представляет всех пользователей каталога. Коллекция **пользователей** для [группы](./group-object-adox.md) представляет только тех пользователей, которые имеют членство в определенной группе.  
  
 Метод [append](./append-method-adox-users.md) для коллекции **пользователей** уникален для ADOX. Вы можете выполнить следующие действия:  
  
-   Добавьте нового пользователя в коллекцию с помощью метода **append** .  
  
 Остальные свойства и методы являются стандартными для коллекций ADO. Вы можете выполнить следующие действия:  
  
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