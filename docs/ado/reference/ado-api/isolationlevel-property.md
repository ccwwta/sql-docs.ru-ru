---
description: Свойство IsolationLevel
title: IsolationLevel, свойство | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Connection15::IsolationLevel
helpviewer_keywords:
- IsolationLevel property
ms.assetid: ea84e4b2-fbf2-4eef-b9ce-796b22e21800
author: rothja
ms.author: jroth
ms.openlocfilehash: 2e6b818ef937328d75d5c5425815dbd931ebdd2a
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100044314"
---
# <a name="isolationlevel-property"></a>Свойство IsolationLevel
Указывает уровень изоляции для объекта [соединения](./connection-object-ado.md) .  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает или возвращает значение [исолатионлевеленум](./isolationlevelenum.md) . Значение по умолчанию — **adXactReadCommitted**.  
  
## <a name="remarks"></a>Remarks  
 Используйте свойство **IsolationLevel** , чтобы установить уровень изоляции объекта **Connection** . Параметр не вступит в силу до следующего вызова метода [примеры BeginTrans](./begintrans-committrans-and-rollbacktrans-methods-ado.md) . Если запрошенный уровень изоляции недоступен, поставщик может вернуть следующий более высокий уровень изоляции, не обновляя свойство **IsolationLevel** .  
  
 Свойство **IsolationLevel** доступно для чтения и записи.  
  
> [!NOTE]
>  **Использование удаленной службы данных** При использовании объекта **подключения** на стороне клиента свойство **IsolationLevel** может быть установлено только в **адксактунспеЦифиед**. Поскольку пользователи работают с отключенными объектами **Recordset** в кэше на стороне клиента, могут возникнуть проблемы с многопользовательской работой. Например, когда два разных пользователя пытаются обновить одну и ту же запись, служба Remote Data Service просто позволяет пользователю, который сначала обновляет запись, получить «выиграть». Запрос на обновление второго пользователя завершится с ошибкой.  
  
## <a name="applies-to"></a>Применение  
 [Объект Connection (ADO)](./connection-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример свойств IsolationLevel и Mode (Visual Basic)](./isolationlevel-and-mode-properties-example-vb.md)   
 [Пример свойств IsolationLevel и Mode (Visual c++)](./isolationlevel-and-mode-properties-example-vc.md)