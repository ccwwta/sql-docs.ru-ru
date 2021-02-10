---
description: Метод Stat
title: Stat, метод | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _Stream::Stat
helpviewer_keywords:
- Stat method [ADO]
ms.assetid: 99a2b2d4-e6b1-4205-b011-72d024ea7240
author: rothja
ms.author: jroth
ms.openlocfilehash: 684e824edc2238d2a6ba18d629c53fbab7ed7d3d
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100051335"
---
# <a name="stat-method"></a>Метод Stat
Извлекает сведения об объекте [потока](./stream-object-ado.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Long stream.Stat(StatStg, StatFlag)  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение **типа Long** , указывающее состояние операции.  
  
#### <a name="parameters"></a>Параметры  
 *статстг*  
 Структура СТАТСТГ, которая будет заполнена сведениями о потоке. Реализация метода **stat** , используемого объектом потока ADO, не заполняет все поля структуры.  
  
 *статфлаг*  
 Указывает, что этот метод не возвращает некоторые члены структуры СТАТСТГ, тем самым сохраняя операцию выделения памяти. Значения берутся из перечисления СТАТФЛАГ. Перечисление СТАТФЛАГ имеет два значения  
  
|Константа|Значение|  
|--------------|-----------|  
|STATFLAG_DEFAULT|0|  
|STATFLAG_NONAME|1|  
  
## <a name="remarks"></a>Remarks  
 Версия метода Stat, реализованного для объекта потока ADO, заполняет следующие поля структуры СТАТСТГ:  
  
 *пвкснаме*  
 Строка, содержащая имя потока, если такой объект доступен, а значение Статфлаг STATFLAG_NONAME не указано.  
  
 *кбсизе*  
 Указывает размер в байтах для потока или массива байтов.  
  
 *мтиме*  
 Показывает время последнего изменения хранилища, потока или массива байтов.  
  
 *CTime*  
 Показывает время создания хранилища, потока или массива байтов.  
  
 *времени atime*  
 Показывает время последнего обращения к хранилищу, потоку или массиву байтов.  
  
 Если в параметре Статфлаг указано значение STATFLAG_NONAME, то имя потока не возвращается.  
  
 Если STATFLAG_NONAME не было указано в параметре Статфлаг и для текущего потока нет доступных имен, это значение будет E_NOTIMPL.  
  
## <a name="applies-to"></a>Применение  
 [Объект Stream (ADO)](./stream-object-ado.md)