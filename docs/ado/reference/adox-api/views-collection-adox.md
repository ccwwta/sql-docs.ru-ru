---
description: Коллекция Views (ADOX)
title: Коллекция Views (ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Catalog::Views
- Views
helpviewer_keywords:
- Views collection [ADOX]
ms.assetid: a55d380c-2b7b-4b57-af74-8ba0b3de0db9
author: rothja
ms.author: jroth
ms.openlocfilehash: c4ac183994402714383320305c64d30a27f3acb5
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100049604"
---
# <a name="views-collection-adox"></a>Коллекция Views (ADOX)
Содержит все объекты [представления](./view-object-adox.md) каталога.  
  
## <a name="remarks"></a>Remarks  
 Метод [append](./append-method-adox-views.md) для коллекции **views** уникален для ADOX. Вы можете выбрать один из следующих вариантов.  
  
-   Добавьте новое представление в коллекцию с помощью метода **append** .  
  
 Остальные свойства и методы являются стандартными для коллекций ADO. Вы можете выбрать один из следующих вариантов.  
  
-   Доступ к представлению в коллекции со свойством [Item](../ado-api/item-property-ado.md) .  
  
-   Возвращает количество представлений, содержащихся в коллекции, с помощью свойства [Count](../ado-api/count-property-ado.md) .  
  
-   Удалите представление из коллекции с помощью метода [Delete](./delete-method-adox-collections.md) .  
  
-   Обновите объекты в коллекции, чтобы отразить текущую схему базы данных методом [Refresh](../ado-api/refresh-method-ado.md) .  
  
 Этот раздел содержит следующий раздел.  
  
-   [Свойства, методы и события коллекции Views](./views-collection-properties-methods-and-events.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример представлений и коллекций полей (Visual Basic)](./views-and-fields-collections-example-vb.md)   
 [Пример метода Append для представлений (Visual Basic)](./views-append-method-example-vb.md)   
 [Пример коллекции Views, свойство CommandText (Visual Basic)](./views-collection-commandtext-property-example-vb.md)   
 [Пример метода Delete представлений (Visual Basic)](./views-delete-method-example-vb.md)   
 [Пример метода Refresh для представлений (Visual Basic)](./views-refresh-method-example-vb.md)   
 [Объект каталога (ADOX)](./catalog-object-adox.md)   
 [Объект View (ADOX)](./view-object-adox.md)