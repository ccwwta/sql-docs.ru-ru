---
description: Коллекция Groups (ADOX)
title: Коллекция Groups (ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Groups
- User::Groups
- Catalog::Groups
helpviewer_keywords:
- Groups collection [ADOX]
ms.assetid: 09aa7b0a-69d5-4564-80a7-20ad8189670f
author: rothja
ms.author: jroth
ms.openlocfilehash: e0cbcc0941c3c2c7158d15bc73f07e4b835db4f3
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99164224"
---
# <a name="groups-collection-adox"></a>Коллекция Groups (ADOX)
Содержит все сохраненные объекты [групп](./group-object-adox.md) каталога или пользователя.  
  
## <a name="remarks"></a>Замечания  
 Коллекция **Groups** [каталога](./catalog-object-adox.md) представляет все учетные записи групп каталога. Коллекция **Groups** для [пользователя](./user-object-adox.md) представляет только группу, к которой принадлежит пользователь.  
  
 Метод [append](./append-method-adox-groups.md) для коллекции **GROUPS** уникален для ADOX. Вы можете выполнить следующие действия:  
  
-   Добавьте новую группу безопасности в коллекцию с помощью метода **append** .  
  
 Остальные свойства и методы являются стандартными для коллекций ADO. Вы можете выполнить следующие действия:  
  
-   Доступ к группе в коллекции со свойством [Item](../ado-api/item-property-ado.md) .  
  
-   Возвращает количество групп, содержащихся в коллекции, с помощью свойства [Count](../ado-api/count-property-ado.md) .  
  
-   Удалите группу из коллекции с помощью метода [Delete](./delete-method-adox-collections.md) .  
  
-   Обновите объекты в коллекции, чтобы отразить текущую схему базы данных методом [Refresh](../ado-api/refresh-method-ado.md) .  
  
> [!NOTE]
>  Перед добавлением объекта **группы** в коллекцию **Groups** объекта **пользователя** объект **группы** с тем же [именем](./name-property-adox.md) , что и один из добавляемых, должен уже существовать в коллекции **Groups** **каталога**.  
  
 Этот раздел содержит следующий раздел.  
  
-   [Свойства, методы и события коллекции Groups](./groups-collection-properties-methods-and-events.md)  
  
## <a name="see-also"></a>См. также:  
 [Объект каталога (ADOX)](./catalog-object-adox.md)   
 [Объект Group (ADOX)](./group-object-adox.md)