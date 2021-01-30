---
description: Свойство ParentCatalog (ADOX)
title: Свойство ParentCatalog (ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _User::get_ParentCatalog
- _Column::ParentCatalog
- _Table::put_ParentCatalog
- _Group::put_ParentCatalog
- _Column::get_ParentCatalog
- _Table::PutParentCatalog
- _Group::putref_ParentCatalog
- _Group::ParentCatalog
- _Column::PutParentCatalog
- _Column::put_ParentCatalog
- _Group::get_ParentCatalog
- _User::put_ParentCatalog
- _User::putref_ParentCatalog
- _Table::get_ParentCatalog
- _Group::PutParentCatalog
- _Table::ParentCatalog
- _Column::GetParentCatalog
- _Table::PutRefParentCatalog
- _User::GetParentCatalog
- _Table::GetParentCatalog
- _Table::putref_ParentCatalog
- _User::PutParentCatalog
- _User::ParentCatalog
- _User::PutRefParentCatalog
- _Group::GetParentCatalog
- _Group::PutRefParentCatalog
helpviewer_keywords:
- ParentCatalog property [ADOX]
ms.assetid: a0bb2ed8-d4cb-4f92-8de7-769bbe0e6273
author: rothja
ms.author: jroth
ms.openlocfilehash: 720d3f5a04d17664b7fa486d084a9d443bd5f2e4
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99169300"
---
# <a name="parentcatalog-property-adox"></a>Свойство ParentCatalog (ADOX)
Указывает родительский каталог объекта таблицы, пользователя или столбца, который предоставляет доступ к свойствам, зависящим от поставщика.  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает и возвращает объект [каталога](./catalog-object-adox.md) . Установка **ParentCatalog** в открытый **Каталог** предоставляет доступ к свойствам, зависящим от поставщика, до добавления таблицы или столбца в коллекцию **каталогов** .  
  
## <a name="remarks"></a>Замечания  
 Некоторые поставщики данных позволяют записывать значения свойств, определяемые поставщиком, только при их создании: то есть когда таблица или столбец добавляются в коллекцию **каталогов** . Чтобы получить доступ к этим свойствам перед добавлением этих объектов в **Каталог**, сначала укажите **Каталог** в свойстве **ParentCatalog** .  
  
 Ошибка возникает при добавлении таблицы или столбца к **каталогу** , отличному от каталога **ParentCatalog**.  
  
## <a name="applies-to"></a>Применение  

:::row:::
    :::column:::
        [Объект Column (ADOX)](./column-object-adox.md)  
    :::column-end:::
    :::column:::
        [Объект Table (ADOX)](./table-object-adox.md)  
    :::column-end:::
    :::column:::
        [Объект User (ADOX)](./user-object-adox.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>См. также:  
 [Пример свойства ParentCatalog (Visual Basic)](./parentcatalog-property-example-vb.md)