---
description: Свойство CommandTimeout (ADO)
title: Свойство CommandTimeout (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Command15::CommandTimeout
helpviewer_keywords:
- CommandTimeout property [ADO]
ms.assetid: c611f857-d6b0-4dca-8925-f4a02e769eb0
author: rothja
ms.author: jroth
ms.openlocfilehash: aa12f6e7c6e2451f6323f4d25dfed6894d7b5c26
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99171466"
---
# <a name="commandtimeout-property-ado"></a>Свойство CommandTimeout (ADO)
Указывает время ожидания при выполнении команды перед завершением попытки и генерацией ошибки.  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает или возвращает **длинное** значение, указывающее время ожидания выполнения команды (в секундах). Значение по умолчанию — 30.  
  
## <a name="remarks"></a>Замечания  
 Используйте свойство **CommandTimeout** для объекта [соединения](./connection-object-ado.md) или объекта [Command](./command-object-ado.md) , чтобы разрешить отмену вызова метода [EXECUTE](./execute-method-ado-command.md) из-за задержки сетевого трафика или интенсивного использования сервера. Если интервал, заданный в свойстве **CommandTimeout** , истекает до завершения выполнения команды, возникает ошибка и ADO отменяет команду. Если присвоить свойству значение 0, то до завершения выполнения ADO будет ждать неограниченно. Убедитесь, что поставщик и источник данных, в которых пишется код, поддерживают функцию **CommandTimeout** .  
  
 Параметр **CommandTimeout** для объекта **соединения** не влияет на параметр **CommandTimeout** в объекте **Command** в том же **соединении**. то есть, свойство **CommandTimeout** объекта **команды** не наследует значение значения **CommandTimeout** объекта **соединения** .  
  
 Для объекта **соединения** свойство **CommandTimeout** остается доступен для чтения и записи после открытия **соединения** .  
  
## <a name="applies-to"></a>Применение  

:::row:::
    :::column:::
        [Объект Command (ADO)](./command-object-ado.md)  
    :::column-end:::
    :::column:::
        [Объект Connection (ADO)](./connection-object-ado.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>См. также:  
 [Пример свойств ActiveConnection, CommandText, CommandTimeout, CommandType, Size и Direction (Visual Basic)](./activeconnection-commandtext-commandtimeout-commandtype-size-example-vb.md)   
 [Пример свойств ActiveConnection, CommandText, CommandTimeout, CommandType, Size и Direction (Visual c++)](./activeconnection-commandtext-commandtimeout-commandtype-size-example-vc.md)   
 [Пример свойств ActiveConnection, CommandText, CommandTimeout, CommandType, Size и Direction (JScript)](./activeconnection-commandtext-timeout-type-size-example-jscript.md)   
 [Свойство ConnectionTimeout (ADO)](./connectiontimeout-property-ado.md)