---
description: Метод GetString (ADO)
title: Метод GetString (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Recordset20::raw_GetString
- Recordset20::GetString
helpviewer_keywords:
- GetString method [ADO]
ms.assetid: 92452940-b2a7-456e-94fc-3780c71da33c
author: rothja
ms.author: jroth
ms.openlocfilehash: d1626dd9ff1c97426a0597b010015adada4c17c7
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99167248"
---
# <a name="getstring-method-ado"></a>Метод GetString (ADO)
Возвращает [набор записей](./recordset-object-ado.md) в виде строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Variant = recordset.GetString(StringFormat, NumRows, ColumnDelimiter, RowDelimiter, NullExpr)  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает **набор записей** как строковый **вариант** (BSTR).  
  
#### <a name="parameters"></a>Параметры  
 *StringFormat*  
 Значение [стрингформатенум](./stringformatenum.md) , указывающее, как **набор записей** должен быть преобразован в строку. Параметры *RowDelimiter*, *ColumnDelimiter* и *Нуллекспр* используются только с *StringFormat* **адклипстринг**.  
  
 *нумровс*  
 Необязательный параметр. Число строк для преобразования в **наборе записей**. Если *нумровс* не указан или превышает общее число строк в **наборе записей**, то преобразуются все строки в **наборе записей** .  
  
 *ColumnDelimiter*  
 Необязательный параметр. Разделитель, используемый между столбцами, если он указан; в противном случае — символ ТАБУЛЯЦИи.  
  
 *RowDelimiter*  
 Необязательный параметр. Разделитель, используемый между строками, если они заданы; в противном случае — символ возврата КАРЕТки.  
  
 *нуллекспр*  
 Необязательный параметр. Выражение, используемое вместо значения NULL, если оно указано, в противном случае — пустая строка.  
  
## <a name="remarks"></a>Замечания  
 Данные строк, но отсутствуют данные схемы, сохраняются в строке. Таким образом, **набор записей** нельзя открыть повторно с помощью этой строки.  
  
 Этот метод эквивалентен методу RDO **жетклипстринг** .  
  
## <a name="applies-to"></a>Применение  
 [Объект Recordset (ADO)](./recordset-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример метода GetString (Visual Basic)](./getstring-method-example-vb.md)