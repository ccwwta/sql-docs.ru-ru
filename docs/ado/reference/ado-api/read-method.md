---
description: Метод Read
title: Метод Read | Документация Майкрософт
ms.prod: sql
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Stream::raw_Read
- _Stream::Read
helpviewer_keywords:
- Read method [ADO]
ms.assetid: 838502de-80f1-4eeb-8838-dd3d9403e567
author: rothja
ms.author: jroth
ms.openlocfilehash: 0adf12bc63745f739aaf8b71a92c660c1c1ad2fd
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99170488"
---
# <a name="read-method"></a>Метод Read
Считывает указанное число байтов из объекта двоичного [потока](./stream-object-ado.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Variant = Stream.Read ( NumBytes)  
```  
  
#### <a name="parameters"></a>Параметры  
 *нумбитес*  
 Необязательный параметр. Значение **типа Long** , указывающее количество байтов для чтения из файла или значения [стреамреаденум](./streamreadenum.md) **адреадалл**, которое является значением по умолчанию.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Метод **Read** считывает указанное число байтов или весь поток из объекта **потока** и возвращает результирующие данные в виде **Variant**.  
  
## <a name="remarks"></a>Замечания  
 Если *нумбитес* больше числа байтов, остающихся в **потоке**, возвращаются только оставшиеся байты. Чтение данных не дополняется в соответствии с длиной, заданной параметром *нумбитес*. Если не осталось байтов для чтения, возвращается Variant со значением NULL. **Чтение** не может быть использовано для чтения в обратном направлении.  
  
> [!NOTE]
>  *Нумбитес* всегда измеряет байты. Для объектов текстового **потока** ([Type](./type-property-ado-stream.md) — **адтипетекст**) используйте [ReadText](./readtext-method.md).  
  
## <a name="applies-to"></a>Применение  
 [Объект Stream (ADO)](./stream-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Метод ReadText](./readtext-method.md)