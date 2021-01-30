---
description: Метод Append (коллекция Columns ADOX)
title: Метод Append (столбцы ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Columns::raw_Append
- Columns::Append
helpviewer_keywords:
- Append method [ADOX]
ms.assetid: 7a46d23c-efef-4ec7-815d-cd3ac86787dd
author: rothja
ms.author: jroth
ms.openlocfilehash: 40abf0ae298b469d0814e8dd3da85a8c8865be78
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99169597"
---
# <a name="append-method-adox-columns"></a>Метод Append (коллекция Columns ADOX)
Добавляет новый объект [Column](./column-object-adox.md) в коллекцию [Columns](./columns-collection-adox.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Columns.Append Column [,Type] [,DefinedSize]  
```  
  
#### <a name="parameters"></a>Параметры  
 *Столбец*  
 Добавляемый объект **Column** или имя создаваемого и добавляемого столбца.  
  
 *Type*  
 Необязательный параметр. Значение типа **Long** , указывающее тип данных столбца. Параметр *типа* соответствует свойству [Type](./type-property-column-adox.md) объекта **Column** .  
  
 *DefinedSize*  
 Необязательный параметр. Значение **типа Long** , указывающее размер столбца. Параметр *DefinedSize* соответствует свойству [DefinedSize](./definedsize-property-adox.md) объекта **Column** .  
  
> [!NOTE]
>  При добавлении **столбца** в коллекцию **Columns** [индекса](./index-object-adox.md) , если **Столбец** не существует в [таблице](./table-object-adox.md) , уже присоединенной к коллекции [таблиц](./tables-collection-adox.md) , возникнет ошибка.  
  
## <a name="applies-to"></a>Применение  
 [Коллекция Columns (ADOX)](./columns-collection-adox.md)  
  
## <a name="see-also"></a>См. также:  
 [Методы добавления столбцов и таблиц, пример свойства Name (Visual Basic)](./columns-and-tables-append-methods-name-property-example-vb.md)   
 [Пример свойств для добавления ключей, типа ключа, RelatedColumn, RelatedTable и UpdateRule (Visual Basic)](./keys-append-method-key-type-relatedcolumn-relatedtable-example-vb.md)   
 [Пример свойства ParentCatalog (Visual Basic)](./parentcatalog-property-example-vb.md)   
 [Метод Append (группы ADOX)](./append-method-adox-groups.md)   
 [Метод Append (индексы ADOX)](./append-method-adox-indexes.md)   
 [Метод Append (ключи ADOX)](./append-method-adox-keys.md)   
 [Метод Append (процедуры ADOX)](./append-method-adox-procedures.md)   
 [Метод Append (таблицы ADOX)](./append-method-adox-tables.md)   
 [Метод Append (пользователи ADOX)](./append-method-adox-users.md)   
 [Метод Append (коллекция Views ADOX)](./append-method-adox-views.md)