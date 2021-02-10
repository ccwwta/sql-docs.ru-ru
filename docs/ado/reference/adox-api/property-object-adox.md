---
description: Объект Property (ADOX)
title: Объект Property (ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
helpviewer_keywords:
- Property object [ADOX]
ms.assetid: 6a56def6-dbe6-4ccc-a491-8d076889f019
author: rothja
ms.author: jroth
ms.openlocfilehash: 3fba73c2f9b0f1c722feaab311f1b74fbcf91a35
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100049794"
---
# <a name="property-object-adox"></a>Объект Property (ADOX)
Представляет характеристику объекта ADOX.  
  
## <a name="remarks"></a>Remarks  
 Объекты ADOX имеют два типа свойств: встроенные и динамические.  
  
 Встроенные свойства — это свойства, которые немедленно доступны для любого нового объекта с помощью синтаксиса MyObject. Property. Они не отображаются как объекты свойств в [коллекции свойств](../ado-api/properties-collection-ado.md)объекта, поэтому, хотя их значения можно изменять, их характеристики изменить нельзя.  
  
 Динамические свойства определяются базовым поставщиком данных и отображаются в коллекции Properties для соответствующего объекта ADOX.  На динамические свойства можно ссылаться только через коллекцию с помощью синтаксиса MyObject. Properties (0) или MyObject. Properties ("имя").  
  
 Нельзя удалить оба типа свойств.  
  
 Объект динамического свойства имеет четыре встроенных свойства.  
  
 Свойство [Name](../ado-api/name-property-ado.md) — это строка, идентифицирующая свойство.  
  
 Свойство [Type](../ado-api/type-property-ado.md) — это целое число, указывающее тип данных свойства.  
  
 Свойство [value](../ado-api/value-property-ado.md) — это вариант, который содержит значение свойства. Value является свойством по умолчанию для объекта Property.  
  
 Свойство [Attributes](../ado-api/attributes-property-ado.md) является длинным значением, указывающим характеристики свойства, характерного для поставщика.  
  
 Этот раздел содержит следующий раздел.  
  
-   [Свойства, методы и события объекта Property (ADOX)](./adox-property-object-properties-methods-and-events.md)