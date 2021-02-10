---
description: Метод Append (коллекция Groups ADOX)
title: Метод Append (группы ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Groups::raw_Append
- Groups::Append
helpviewer_keywords:
- Append method [ADOX]
ms.assetid: 56b94fc6-7ef0-4e4a-82a3-033b94c46036
author: rothja
ms.author: jroth
ms.openlocfilehash: 846475567fb15e549f96094ca55a1881d8888ce5
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100050535"
---
# <a name="append-method-adox-groups"></a>Метод Append (коллекция Groups ADOX)
Добавляет новый объект [группы](./group-object-adox.md) в коллекцию [Groups](./groups-collection-adox.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Groups.Append Group  
```  
  
#### <a name="parameters"></a>Параметры  
 *Группа*  
 Добавляемый объект **группы** или имя группы для создания и добавления.  
  
## <a name="remarks"></a>Remarks  
 Коллекция **Groups** [каталога](./catalog-object-adox.md) представляет все учетные записи групп каталога. Коллекция **Groups** для [пользователя](./user-object-adox.md) представляет только группу, к которой принадлежит пользователь.  
  
 Если поставщик не поддерживает создание групп, возникнет ошибка.  
  
> [!NOTE]
>  Перед добавлением объекта **группы** в коллекцию **Groups** объекта **пользователя** объект **группы** с тем же [именем](./name-property-adox.md) , что и один из добавляемых, должен уже существовать в коллекции **Groups** **каталога**.  
  
## <a name="applies-to"></a>Применение  
 [Коллекция Groups (ADOX)](./groups-collection-adox.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример добавления групп и пользователей, методы ChangePassword (Visual Basic)](./groups-and-users-append-changepassword-methods-example-vb.md)   
 [Метод Append (столбцы ADOX)](./append-method-adox-columns.md)   
 [Метод Append (индексы ADOX)](./append-method-adox-indexes.md)   
 [Метод Append (ключи ADOX)](./append-method-adox-keys.md)   
 [Метод Append (процедуры ADOX)](./append-method-adox-procedures.md)   
 [Метод Append (таблицы ADOX)](./append-method-adox-tables.md)   
 [Метод Append (пользователи ADOX)](./append-method-adox-users.md)   
 [Метод Append (коллекция Views ADOX)](./append-method-adox-views.md)