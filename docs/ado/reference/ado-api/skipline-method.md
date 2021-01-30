---
description: Метод SkipLine
title: Метод Скиплине | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _Stream::raw_SkipLine
- _Stream::SkipLine
helpviewer_keywords:
- Skipline method [ADO]
ms.assetid: 0abc00fe-ee09-4c8e-b1f2-48ee9c5f3329
author: rothja
ms.author: jroth
ms.openlocfilehash: 826e90b65131453bb50cc70e3efbc3ad8796c89f
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99166534"
---
# <a name="skipline-method"></a>Метод SkipLine
Пропускает одну целую строку при чтении текстового [потока](./stream-object-ado.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Stream.SkipLine  
```  
  
## <a name="remarks"></a>Remarks  
 Все символы до и включительно разделитель следующей строки пропускаются. По умолчанию [LineSeparator](./lineseparator-property-ado.md) имеет значение **адкрлф**. Если вы попытаетесь пропустить предыдущие [EOS](./eos-property.md), текущее расположение останется в **EOS**.  
  
 Метод **скиплине** используется с текстовыми потоками ([тип](./type-property-ado-stream.md) — **адтипетекст**).  
  
## <a name="applies-to"></a>Применение  
 [Объект Stream (ADO)](./stream-object-ado.md)