---
description: Свойство LineSeparator (ADO)
title: Свойство LineSeparator (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _Stream::LineSeparator
helpviewer_keywords:
- LineSeparator property [ADO]
ms.assetid: 0b20fbb8-6b83-48ec-b442-f96c8a4bafbb
author: rothja
ms.author: jroth
ms.openlocfilehash: fa50003834cf83017ec9eaf4581ed1cff7bd26bc
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100044284"
---
# <a name="lineseparator-property-ado"></a>Свойство LineSeparator (ADO)
Указывает двоичный символ, используемый в качестве разделителя строк в объектах текстового [потока](./stream-object-ado.md) .  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает или возвращает значение [линесепараторсенум](./lineseparatorsenum.md) , указывающее символ разделителя строки, используемый в **потоке**. Значение по умолчанию — **адкрлф**.  
  
## <a name="remarks"></a>Remarks  
 **LineSeparator** используется для интерпретации строк при считывании содержимого текстового **потока**. Строки можно пропустить с помощью метода [скиплине](./skipline-method.md) .  
  
 **LineSeparator** используется только с объектами **потока** текста ([тип](./type-property-ado-stream.md) — **адтипетекст**). Это свойство игнорируется, если **Type** имеет значение **адтипебинари**.  
  
## <a name="applies-to"></a>Применение  
 [Объект Stream (ADO)](./stream-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Объект Stream (ADO)](./stream-object-ado.md)