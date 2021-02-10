---
description: Метод Append (коллекция Keys ADOX)
title: Метод Append (ключи ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Keys::Append
- Keys::raw_Append
helpviewer_keywords:
- Append method [ADOX]
ms.assetid: 215a5391-f422-42ec-99ea-4e6fbb5d3d64
author: rothja
ms.author: jroth
ms.openlocfilehash: 573bfb24f68896f647f4c0d9ff5867ee1d38e5fb
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100050515"
---
# <a name="append-method-adox-keys"></a>Метод Append (коллекция Keys ADOX)
Добавляет новый объект [Key](./key-object-adox.md) в коллекцию [Keys](./keys-collection-adox.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Keys.Append Key [,KeyType] [,Column] [,RelatedTable] [,RelatedColumn]  
```  
  
#### <a name="parameters"></a>Параметры  
 *Key*  
 Добавляемый объект **Key** или имя создаваемого и добавляемого ключа.  
  
 *KeyType*  
 Необязательный элемент. Значение типа **Long** , указывающее тип ключа. Параметр *Key* соответствует свойству [Type](./type-property-key-adox.md) **ключевого** объекта.  
  
 *Столбец*  
 Необязательный элемент. **Строковое** значение, указывающее имя индексируемого столбца. Параметр *Columns* соответствует значению свойства [Name](./name-property-adox.md) объекта [Column](./column-object-adox.md) .  
  
 *RelatedTable*  
 Необязательный элемент. **Строковое** значение, указывающее имя связанной таблицы. Параметр *RelatedTable* соответствует значению свойства **Name** объекта [Table](./table-object-adox.md) .  
  
 *RelatedColumn*  
 Необязательный элемент. **Строковое** значение, указывающее имя связанного столбца для внешнего ключа. Параметр *RelatedColumn* соответствует значению свойства **Name** объекта [Column](./column-object-adox.md) .  
  
## <a name="remarks"></a>Remarks  
 Параметр *Columns* может принимать либо имя столбца, либо массив имен столбцов.  
  
## <a name="applies-to"></a>Применение  
 [Коллекция Keys (ADOX)](./keys-collection-adox.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример свойств для добавления ключей, типа ключа, RelatedColumn, RelatedTable и UpdateRule (Visual Basic)](./keys-append-method-key-type-relatedcolumn-relatedtable-example-vb.md)   
 [Метод Append (столбцы ADOX)](./append-method-adox-columns.md)   
 [Метод Append (группы ADOX)](./append-method-adox-groups.md)   
 [Метод Append (индексы ADOX)](./append-method-adox-indexes.md)   
 [Метод Append (процедуры ADOX)](./append-method-adox-procedures.md)   
 [Метод Append (таблицы ADOX)](./append-method-adox-tables.md)   
 [Метод Append (пользователи ADOX)](./append-method-adox-users.md)   
 [Метод Append (коллекция Views ADOX)](./append-method-adox-views.md)