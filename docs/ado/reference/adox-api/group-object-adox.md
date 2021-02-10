---
description: Объект Group (ADOX)
title: Объект Group (ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Group
helpviewer_keywords:
- group object [ADOX]
ms.assetid: 55ef0ade-68ea-4da5-8aa5-4cd27d1f6d1e
author: rothja
ms.author: jroth
ms.openlocfilehash: b72179e91ad4c9742ffd42a70ff37e33f402d8e3
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100054199"
---
# <a name="group-object-adox"></a>Объект Group (ADOX)
Представляет учетную запись группы, имеющую разрешения на доступ в защищенной базе данных.  
  
## <a name="remarks"></a>Remarks  
 Коллекция [Groups](./groups-collection-adox.md) [каталога](./catalog-object-adox.md) представляет все учетные записи групп каталога. Коллекция **Groups** для [пользователя](./user-object-adox.md) представляет только группу, к которой принадлежит пользователь.  
  
 С помощью свойств, коллекций и методов объекта **Group** можно:  
  
-   Найдите группу с помощью свойства [Name](./name-property-adox.md) .  
  
-   Определите, имеет ли группа разрешения на чтение, запись или удаление [с помощью методов](./getpermissions-method-adox.md) [SetPermissions](./setpermissions-method-adox.md) и.  
  
-   Доступ к учетным записям пользователей, имеющим членство в группе, с помощью коллекции [пользователей](./users-collection-adox.md) .  
  
-   Доступ к свойствам, зависящим от поставщика, с коллекцией [свойств](../ado-api/properties-collection-ado.md) .  
  
 Этот раздел содержит следующий раздел.  
  
-   [Свойства, методы и события объекта Group](./group-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>См. также:  
 [Коллекция Groups (ADOX)](./groups-collection-adox.md)   
 [Коллекция Users (ADOX)](./users-collection-adox.md)