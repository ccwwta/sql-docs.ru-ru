---
description: Объект Procedure (ADOX)
title: Объект процедуры (ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Procedure
helpviewer_keywords:
- Procedure object [ADOX]
ms.assetid: 927bcf3e-32f5-4a80-98d3-600779f0732e
author: rothja
ms.author: jroth
ms.openlocfilehash: fec4b21cf4aa619fba72f5d62fff7f6e34506de5
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100053879"
---
# <a name="procedure-object-adox"></a>Объект Procedure (ADOX)
Представляет хранимую процедуру. При использовании в сочетании с объектом [команды](../ado-api/command-object-ado.md) ADO объект **процедуры** можно использовать для добавления, удаления или изменения хранимых процедур.  
  
## <a name="remarks"></a>Remarks  
 Объект **процедуры** позволяет создать хранимую процедуру, не зная и не используя синтаксис создания процедуры поставщика.  
  
 Свойства объекта **процедуры** позволяют:  
  
-   Найдите процедуру с помощью свойства [Name](./name-property-adox.md) .  
  
-   Укажите объект **команды** ADO, который можно использовать для создания или выполнения процедуры с помощью свойства [Command](./command-property-adox.md) .  
  
-   Возвращает сведения о дате с помощью свойств [DateCreated](./datecreated-property-adox.md) и [DateModified](./datemodified-property-adox.md) .  
  
 Этот раздел содержит следующий раздел.  
  
-   [Свойства, методы и события объекта Procedure](./procedure-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример свойств Command и CommandText (Visual Basic)](./command-and-commandtext-properties-example-vb.md)   
 [Коллекция Parameters, пример свойства Command (Visual Basic)](./parameters-collection-command-property-example-vb.md)   
 [Пример метода Append для процедур (Visual Basic)](./procedures-append-method-example-vb.md)   
 [Пример метода Delete процедур (Visual Basic)](./procedures-delete-method-example-vb.md)   
 [Коллекция Procedures (ADOX)](./procedures-collection-adox.md)