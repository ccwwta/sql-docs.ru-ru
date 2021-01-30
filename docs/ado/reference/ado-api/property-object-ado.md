---
description: Объект Property (ADO)
title: Объект Property (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Property
helpviewer_keywords:
- Property object [ADO]
ms.assetid: b2a4767c-03c7-4935-a3bc-df3e1a38a009
author: rothja
ms.author: jroth
ms.openlocfilehash: a24503889e8bd7deab3bca6072da9114f0a0efdd
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99170532"
---
# <a name="property-object-ado"></a>Объект Property (ADO)
Представляет динамическую характеристику объекта ADO, определяемого поставщиком.  
  
## <a name="remarks"></a>Замечания  
 Объекты ADO имеют два типа свойств: встроенные и динамические.  
  
 Встроенные свойства — это свойства, реализованные в ADO и немедленно доступные для любого нового объекта с использованием `MyObject.Property` синтаксиса. Они не отображаются как объекты **свойств** в коллекции [свойств](./properties-collection-ado.md) объекта, поэтому, хотя их значения можно изменять, их характеристики изменить нельзя.  
  
 Динамические свойства определяются базовым поставщиком данных и отображаются в коллекции **Properties** для соответствующего объекта ADO. Например, свойство, относящееся к поставщику, может указывать, поддерживает ли объект [набора записей](./recordset-object-ado.md) транзакции или обновление. Эти дополнительные свойства будут отображаться как объекты **свойств** в коллекции **свойств** объекта **набора записей** . На динамические свойства можно ссылаться только через коллекцию, используя `MyObject.Properties(0)` `MyObject.Properties("Name")` синтаксис или.  
  
 Нельзя удалить оба типа свойств.  
  
 Объект динамического **Свойства** имеет четыре встроенных свойства.  
  
-   Свойство [Name](./name-property-ado.md) — это строка, идентифицирующая свойство.  
  
-   Свойство [Type](./type-property-ado.md) — это целое число, указывающее тип данных свойства.  
  
-   Свойство [value](./value-property-ado.md) — это вариант, который содержит значение свойства. **Value** является свойством по умолчанию для объекта **Property** .  
  
-   Свойство [Attributes](./attributes-property-ado.md) является длинным значением, указывающим характеристики свойства, характерного для поставщика.  
  
 Этот раздел содержит следующий раздел.  
  
-   [Свойства, методы и события объекта Property](./property-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>См. также:  
 [Объект Command (ADO)](./command-object-ado.md)   
 [Объект Connection (ADO)](./connection-object-ado.md)   
 [Объект Field](./field-object.md)   
 [Коллекция Properties (ADO)](./properties-collection-ado.md)   
 [Объект Recordset (ADO)](./recordset-object-ado.md)