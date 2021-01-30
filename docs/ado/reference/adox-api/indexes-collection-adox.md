---
description: Коллекция Indexes (ADOX)
title: Коллекция indexes (ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Table::Indexes
- Indexes
helpviewer_keywords:
- Indexes collection [ADOX]
ms.assetid: 184cf536-455c-42be-bf1c-a5c25bade961
author: rothja
ms.author: jroth
ms.openlocfilehash: 74147f1168e9bf9789c0ab1111daa27536dfd64e
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99172019"
---
# <a name="indexes-collection-adox"></a>Коллекция Indexes (ADOX)
Содержит все объекты [индекса](./index-object-adox.md) таблицы.  
  
## <a name="remarks"></a>Замечания  
 Метод [append](./append-method-adox-indexes.md) для коллекции **индексов** уникален для ADOX. Вы можете выполнить следующие действия:  
  
-   Добавьте новый индекс в коллекцию с помощью метода **append** .  
  
 Остальные свойства и методы являются стандартными для коллекций ADO. Вы можете выполнить следующие действия:  
  
-   Доступ к индексу в коллекции со свойством [Item](../ado-api/item-property-ado.md) .  
  
-   Возвращает количество индексов, содержащихся в коллекции, со свойством [Count](../ado-api/count-property-ado.md) .  
  
-   Удалите индекс из коллекции с помощью метода [Delete](./delete-method-adox-collections.md) .  
  
-   Обновите объекты в коллекции, чтобы отразить текущую схему базы данных методом [Refresh](../ado-api/refresh-method-ado.md) .  
  
 Этот раздел содержит следующий раздел.  
  
-   [Свойства, методы и события коллекции Indexes](./indexes-collection-properties-methods-and-events.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример метода Append для индексов (Visual Basic)](./indexes-append-method-example-vb.md)   
 [Объект Index (ADOX)](./index-object-adox.md)