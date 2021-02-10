---
description: Объект Key (ADOX)
title: Ключевой объект (ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Key
helpviewer_keywords:
- Key object [ADOX]
ms.assetid: 55f116fe-4d56-4892-bffe-0cdd6fc727c9
author: rothja
ms.author: jroth
ms.openlocfilehash: b0e2cdd3dcb1d6d0772e1b7508bee8063089a4e3
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100054079"
---
# <a name="key-object-adox"></a>Объект Key (ADOX)
Представляет первичное, внешнее или уникальное ключевое поле из таблицы базы данных.  
  
## <a name="remarks"></a>Remarks  
 Следующий код создает новый **ключ**:  
  
```  
Dim obj As New Key  
```  
  
 Свойства и коллекции **ключевого** объекта позволяют:  
  
-   Найдите ключ со свойством [Name](./name-property-adox.md) .  
  
-   Определите, является ли ключ первичным, внешним или уникальным с помощью свойства [Type](./type-property-key-adox.md) .  
  
-   Получите доступ к столбцам базы данных ключа с помощью коллекции [Columns](./columns-collection-adox.md) .  
  
-   Укажите имя связанной таблицы со свойством [RelatedTable](./relatedtable-property-adox.md) .  
  
-   Определите действие, выполняемое при удалении или обновлении первичного ключа с помощью свойств [DeleteRule](./deleterule-property-adox.md) и [UpdateRule](./updaterule-property-adox.md) .  
  
 Этот раздел содержит следующий раздел.  
  
-   [Свойства, методы и события объекта Key](./key-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример свойств для добавления ключей, типа ключа, RelatedColumn, RelatedTable и UpdateRule (Visual Basic)](./keys-append-method-key-type-relatedcolumn-relatedtable-example-vb.md)   
 [Коллекция Columns (ADOX)](./columns-collection-adox.md)   
 [Коллекция Keys (ADOX)](./keys-collection-adox.md)