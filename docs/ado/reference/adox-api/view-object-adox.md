---
description: Объект View (ADOX)
title: Просмотр объекта (ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- View
helpviewer_keywords:
- View object [ADOX]
ms.assetid: 653421ce-7b94-43d0-9bc6-4900f8f2af45
author: rothja
ms.author: jroth
ms.openlocfilehash: 227a52fb1ee89777d1e198e96e253ef8dd5bb979
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100049664"
---
# <a name="view-object-adox"></a>Объект View (ADOX)
Представляет отфильтрованный набор записей или виртуальную таблицу. При использовании в сочетании с объектом [команды](../ado-api/command-object-ado.md) ADO объект **View** можно использовать для добавления, удаления или изменения представлений.  
  
## <a name="remarks"></a>Remarks  
 Представление — это виртуальная таблица, созданная из других таблиц или представлений базы данных. Объект **View** позволяет создавать представления, не зная и не используя синтаксис создания представления поставщика.  
  
 Свойства объекта **представления** позволяют:  
  
-   Определяет представление с помощью свойства [Name](./name-property-adox.md) .  
  
-   Укажите объект **команды** ADO, который может быть использован для добавления, удаления или изменения представлений с помощью свойства [Command](./command-property-adox.md) .  
  
-   Возвращает сведения о дате с помощью свойств [DateCreated](./datecreated-property-adox.md) и [DateModified](./datemodified-property-adox.md) .  
  
 Этот раздел содержит следующий раздел.  
  
-   [Свойства, методы и события объекта View](./view-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример представлений и коллекций полей (Visual Basic)](./views-and-fields-collections-example-vb.md)   
 [Пример метода Append для представлений (Visual Basic)](./views-append-method-example-vb.md)   
 [Пример коллекции Views, свойство CommandText (Visual Basic)](./views-collection-commandtext-property-example-vb.md)   
 [Пример метода Delete представлений (Visual Basic)](./views-delete-method-example-vb.md)   
 [Коллекция Views (ADOX)](./views-collection-adox.md)