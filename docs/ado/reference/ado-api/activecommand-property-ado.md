---
description: Свойство ActiveCommand (ADO)
title: Свойство ActiveCommand (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Recordset20::ActiveCommand
helpviewer_keywords:
- ActiveCommand property [ADO]
ms.assetid: fb4088d5-5968-42d6-aeaa-3955046bb4da
author: rothja
ms.author: jroth
ms.openlocfilehash: 0a8d8dab4944cfa2d43bc571442e294699154f12
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99159265"
---
# <a name="activecommand-property-ado"></a>Свойство ActiveCommand (ADO)
Указывает объект [Command](./command-object-ado.md) , который создал связанный объект [набора записей](./recordset-object-ado.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает **значение типа Variant** , содержащее объект **Command** . По умолчанию используется пустая ссылка на объект.  
  
## <a name="remarks"></a>Замечания  
 Свойство **ActiveCommand** доступно только для чтения.  
  
 Если объект **команды** не использовался для создания текущего **набора записей**, возвращается ссылка на **пустой** объект.  
  
 Это свойство используется для поиска связанного объекта **Command** , если предоставлен только результирующий объект **набора записей** .  
  
## <a name="applies-to"></a>Применение  
 [Объект Recordset (ADO)](./recordset-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример свойства ActiveCommand (Visual Basic)](./activecommand-property-example-vb.md)   
 [Пример свойства ActiveCommand (JScript)](./activecommand-property-example-jscript.md)   
 [Пример свойства ActiveCommand (Visual c++)](./activecommand-property-example-vc.md)   
 [Объект Command (ADO)](./command-object-ado.md)