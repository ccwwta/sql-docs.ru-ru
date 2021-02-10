---
description: Метод SetEOS
title: Метод Сетеос | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _Stream::raw_SetEOS
- _Stream::SetEOS
helpviewer_keywords:
- SetEOS method [ADO]
ms.assetid: 707c18ca-6a56-4970-bbd6-ae1fb86a0b8a
author: rothja
ms.author: jroth
ms.openlocfilehash: a68804b31f36c108096b5f0bb6b3b1d20b4109cd
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100040574"
---
# <a name="seteos-method"></a>Метод SetEOS
Задает расположение, которое является концом потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Stream.SetEOS  
```  
  
## <a name="remarks"></a>Remarks  
 **Сетеос** обновляет значение свойства [EOS](./eos-property.md) , делая текущей [позицией](./position-property-ado.md) конец потока. Все байты или символы, следующие за текущей позицией, усекаются.  
  
 Поскольку [Write](./write-method.md), [WriteText](./writetext-method.md)и [CopyTo](./copyto-method-ado.md) не усекаются какие-либо лишние значения в существующих объектах **потока** , можно усечь эти байты или символы, установив новую точку конца потока с помощью **сетеос**.  
  
> [!CAUTION]
>  Если задать для **EOS** расположение до фактического конца потока, будут потеряны все данные после новой точки **EOS** .  
  
## <a name="applies-to"></a>Применение  
 [Объект Stream (ADO)](./stream-object-ado.md)