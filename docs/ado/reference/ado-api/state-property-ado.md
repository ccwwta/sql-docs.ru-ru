---
description: Свойство State (ADO)
title: Свойство State (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Command25::State
helpviewer_keywords:
- State property [ADO]
ms.assetid: 0b993bac-2653-40b1-bcbb-5b57b6aae2bf
author: rothja
ms.author: jroth
ms.openlocfilehash: 7357d21aa58bca15e1fbbeb3c9cec542ef40ce8b
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100051325"
---
# <a name="state-property-ado"></a>Свойство State (ADO)
Указывает для всех применимых объектов, является ли состояние объекта открытым или закрытым. Если объект выполняет асинхронный метод, указывает, является ли текущее состояние объекта подключением, выполнением или извлечением.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение **типа Long** , которое может быть значением [обжектстатинум](./objectstateenum.md) . Значение по умолчанию — **адстатеклосед**.  
  
## <a name="remarks"></a>Remarks  
 Свойство **State** можно использовать для определения текущего состояния данного объекта в любое время.  
  
 Свойство **State** объекта может иметь сочетание значений. Например, если выполняется инструкция, это свойство будет иметь объединенное значение **адстатеопен** и **адстатиксекутинг**.  
  
 Свойство **State** доступно только для чтения.  
  
## <a name="applies-to"></a>Применение  

:::row:::
    :::column:::
        [Объект Command (ADO)](./command-object-ado.md)  
        [Объект Connection (ADO)](./connection-object-ado.md)  
    :::column-end:::
    :::column:::
        [Объект Record (ADO)](./record-object-ado.md)  
        [Объект Recordset (ADO)](./recordset-object-ado.md)  
    :::column-end:::
    :::column:::
        [Объект Stream (ADO)](./stream-object-ado.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>См. также:  
 [Пример свойств ConnectionString, ConnectionTimeout и State (Visual Basic)](./connectionstring-connectiontimeout-and-state-properties-example-vb.md)   
 [Пример свойств ConnectionString, ConnectionTimeout и State (Visual c++)](./connectionstring-connectiontimeout-and-state-properties-example-vc.md)