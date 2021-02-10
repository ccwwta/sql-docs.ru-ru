---
description: PositionEnum
title: Поситионенум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- PositionEnum
helpviewer_keywords:
- PositionEnum enumeration
ms.assetid: e69af0a5-3405-4b72-9c6e-6b188ff746fd
author: rothja
ms.author: jroth
ms.openlocfilehash: 6c563c2d548d56b5b87273a4b3e5c05ef2cdff6d
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100041034"
---
# <a name="positionenum"></a>PositionEnum
Задает текущую позиции указателя записи в [наборе записей](./recordset-object-ado.md).  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**adPosBOF**|-2|Указывает, что указатель текущей записи находится на BOF (то есть свойство [BOF](./bof-eof-properties-ado.md) имеет **значение true**).|  
|**adPosEOF**|–3|Указывает, что указатель текущей записи находится в EOF (то есть свойство [EOF](./bof-eof-properties-ado.md) имеет **значение true**).|  
|**adPosUnknown**|-1|Указывает, что **набор записей** пуст, Текущая заданная позицией неизвестна или поставщик не поддерживает свойство [примеры absolutepage](./absolutepage-property-ado.md) или [примеры AbsolutePosition](./absoluteposition-property-ado.md) .|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com. MS. WFC. Data**  
  
|Константа|  
|--------------|  
|Адоенумс. позиционирование. BOF|  
|Адоенумс. расположение. EOF|  
|Адоенумс. позиционирование. неизвестно|  
  
## <a name="applies-to"></a>Применение  

:::row:::
    :::column:::
        [Свойство AbsolutePage (ADO)](./absolutepage-property-ado.md)  
    :::column-end:::
    :::column:::
        [Свойство AbsolutePosition (ADO)](./absoluteposition-property-ado.md)  
    :::column-end:::
:::row-end:::