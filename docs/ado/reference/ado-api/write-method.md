---
description: Метод Write
title: Метод Write | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _Stream::raw_Write
- _Stream::Write
helpviewer_keywords:
- Write method [ADO]
ms.assetid: 02982e6a-ac5f-4af2-b82e-ce12534b84b2
author: rothja
ms.author: jroth
ms.openlocfilehash: 0d37c1ec3650a4d10d98021bea3b27e996d43e45
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99172344"
---
# <a name="write-method"></a>Метод Write
Записывает двоичные данные в объект [потока](./stream-object-ado.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Stream.Write Buffer  
```  
  
#### <a name="parameters"></a>Параметры  
 *Буфер*  
 **Значение типа Variant** , содержащее массив байтов для записи.  
  
## <a name="remarks"></a>Замечания  
 Указанные байты записываются в объект **потока** без промежуточных пробелов между каждым байтом.  
  
 Текущей [позицией](./position-property-ado.md) присваивается байт, следующий за записанными данными. Метод **Write** не усекает остальные данные в потоке. Если вы хотите усечь эти байты, вызовите [сетеос](./seteos-method.md).  
  
 Если вы пишете после текущей позиции [EOS](./eos-property.md) , [Размер](./size-property-ado-stream.md) **потока** будет увеличен, чтобы вместить новые байты, а **EOS** перейдет к новому байтовому байту в **потоке**.  
  
> [!NOTE]
>  Метод **Write** используется с двоичными потоками ([Type](./type-property-ado-stream.md) — **адтипебинари**). Для текстовых потоков (**Type** — **Адтипетекст**) используйте [WriteText](./writetext-method.md).  
  
## <a name="applies-to"></a>Применение  
 [Объект Stream (ADO)](./stream-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Метод WriteText](./writetext-method.md)