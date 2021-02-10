---
description: StreamReadEnum
title: Стреамреаденум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- StreamReadEnum
helpviewer_keywords:
- StreamReadEnum enumeration [ADO]
ms.assetid: cfa1b416-003a-436f-a21b-bd2397e54db3
author: rothja
ms.author: jroth
ms.openlocfilehash: 8fe599d5a737cb1f7d1eef0120c5e0b18d2de31a
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100056569"
---
# <a name="streamreadenum"></a>StreamReadEnum
Указывает, следует ли считывать весь поток или следующую строку из объекта [потока](./stream-object-ado.md) .  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**adReadAll**|-1|По умолчанию. Считывает все байты из потока от текущей позицией до маркера [EOS](./eos-property.md) . Это единственное допустимое значение **стреамреаденум** с двоичными потоками ([тип](./type-property-ado-stream.md) — **адтипебинари**).|  
|**адреадлине**|-2|Считывает следующую строку из потока (назначается свойством [LineSeparator](./lineseparator-property-ado.md) ).|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Эти константы не имеют эквивалентов ADO/WFC.  
  
## <a name="applies-to"></a>Применение  

:::row:::
    :::column:::
        [Метод Read](./read-method.md)  
    :::column-end:::
    :::column:::
        [Метод ReadText](./readtext-method.md)  
    :::column-end:::
:::row-end:::