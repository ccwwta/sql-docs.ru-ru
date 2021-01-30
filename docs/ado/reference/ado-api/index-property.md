---
description: Свойство Index
title: Свойство index | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Recordset21::Index
helpviewer_keywords:
- Index property
ms.assetid: 1c79e271-21ec-41a8-8163-c5e89f0001a7
author: rothja
ms.author: jroth
ms.openlocfilehash: 9e8c346ac48092d7a5dcaf09068bb64d63316a38
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99170962"
---
# <a name="index-property"></a>Свойство Index
Указывает имя индекса, действующего в настоящий момент для объекта [Recordset](./recordset-object-ado.md) .  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает или возвращает **строковое** значение, представляющее собой имя индекса.  
  
## <a name="remarks"></a>Замечания  
 Индекс, указанный в свойстве **index** , должен быть ранее объявлен в базовой таблице базового объекта **Recordset** . Это означает, что индекс должен быть объявлен программным образом как объект [индекса](../adox-api/index-object-adox.md) ADOX или при создании базовой таблицы.  
  
 Если индекс не может быть установлен, возникнет ошибка времени выполнения. Свойство **index** не может быть задано при следующих условиях:  
  
-   В обработчике событий [виллчанжерекордсет](./willchangerecordset-and-recordsetchangecomplete-events-ado.md) или **рекордсетчанжекомплете** .  
  
-   Значение, если **набор записей** по-прежнему исполняет операцию (которая может быть определена свойством [State](./state-property-ado.md) ).  
  
-   Значение, если для **набора записей** задан фильтр со свойством [Filter](./filter-property.md) .  
  
 Свойство **index** всегда может быть установлено успешно, если **набор записей** закрыт, но **набор записей** не будет открыт успешно, или индекс не будет использоваться, если базовый поставщик не поддерживает индексы.  
  
 Если индекс может быть установлен, текущая позиция строки может измениться. Это приведет к обновлению свойства [примеры AbsolutePosition](./absoluteposition-property-ado.md) и запустит события **виллчанжерекордсет**, **рекордсетчанжекомплете**, [виллмове](./willmove-and-movecomplete-events-ado.md)и [мовекомплете](./willmove-and-movecomplete-events-ado.md) .  
  
 Если индекс можно задать и свойство [LockType](./locktype-property-ado.md) имеет значение **адлоккпессимистик** или **adLockOptimistic**, то выполняется неявная операция [UpdateBatch](./updatebatch-method.md) . Это освобождает текущие и затронутые группы. Все существующие фильтры освобождаются, и текущая строка строки изменяется на первую строку переупорядоченного **набора записей**.  
  
 Свойство **index** используется в сочетании с методом [Seek](./seek-method.md) . Если базовый поставщик не поддерживает свойство **index** , и поэтому метод **Seek** , попробуйте использовать вместо него метод [Find](./find-method-ado.md) . Определите, поддерживает ли объект **набора записей** индексы с [поддержкой](./supports-method.md)метода **(адиндекс)** .  
  
 Встроенное свойство **индекса** не связано с динамическим свойством [optimize](./optimize-property-dynamic-ado.md) , хотя они работают с индексами.  
  
## <a name="applies-to"></a>Применение  
 [Объект Recordset (ADO)](./recordset-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример метода Seek и свойства Index (Visual Basic)](./seek-method-and-index-property-example-vb.md)   
 [Объект index (ADOX)](../adox-api/index-object-adox.md)   
 [Метод Seek](./seek-method.md)