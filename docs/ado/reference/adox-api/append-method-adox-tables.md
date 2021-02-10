---
description: Метод Append (коллекция Tables ADOX)
title: Метод Append (таблицы ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Tables::Append
- Tables::raw_Append
helpviewer_keywords:
- Append method [ADOX]
ms.assetid: a362ed51-314c-4783-9598-538dbf755f3d
author: rothja
ms.author: jroth
ms.openlocfilehash: d7f8ccacd9b81205ddd58a1b58290548db8bec92
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100050485"
---
# <a name="append-method-adox-tables"></a>Метод Append (коллекция Tables ADOX)
Добавляет новый объект [Table](./table-object-adox.md) в коллекцию [Tables](./tables-collection-adox.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Tables.Append Table  
```  
  
#### <a name="parameters"></a>Параметры  
 *Таблица*  
 Значение **типа Variant** , содержащее ссылку на **таблицу** для добавления или имя таблицы для создания и добавления.  
  
## <a name="remarks"></a>Remarks  
 Если поставщик не поддерживает создание таблиц, возникнет ошибка.  
  
## <a name="applies-to"></a>Применение  
 [Коллекция Tables (ADOX)](./tables-collection-adox.md)  
  
## <a name="see-also"></a>См. также:  
 [Методы добавления столбцов и таблиц, пример свойства Name (Visual Basic)](./columns-and-tables-append-methods-name-property-example-vb.md)   
 [Пример свойства ParentCatalog (Visual Basic)](./parentcatalog-property-example-vb.md)   
 [Метод Append (столбцы ADOX)](./append-method-adox-columns.md)   
 [Метод Append (группы ADOX)](./append-method-adox-groups.md)   
 [Метод Append (индексы ADOX)](./append-method-adox-indexes.md)   
 [Метод Append (ключи ADOX)](./append-method-adox-keys.md)   
 [Метод Append (процедуры ADOX)](./append-method-adox-procedures.md)   
 [Метод Append (пользователи ADOX)](./append-method-adox-users.md)   
 [Метод Append (коллекция Views ADOX)](./append-method-adox-views.md)