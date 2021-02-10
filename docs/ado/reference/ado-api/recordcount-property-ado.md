---
description: Свойство RecordCount (ADO)
title: Свойство RecordCount (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 03/20/2018
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Recordset15::RecordCount
- Recordset15::GetRecordCount
- Recordset15::get_RecordCount
helpviewer_keywords:
- RecordCount property [ADO]
ms.assetid: 834f0121-394a-44d4-ad7d-999b43a6fe63
author: rothja
ms.author: jroth
ms.openlocfilehash: a4fb478b2320ac2f216ae0d0f1a175a94d346813
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100051865"
---
# <a name="recordcount-property-ado"></a>Свойство RecordCount (ADO)

Указывает количество записей в объекте [набора записей](./recordset-object-ado.md) .
  
## <a name="return-value"></a>Возвращаемое значение

Возвращает значение **типа Long** , указывающее количество записей в **наборе записей**.
  
## <a name="remarks"></a>Remarks

Используйте свойство **RecordCount** , чтобы узнать, сколько записей находится в объекте **набора записей** . Свойство возвращает значение-1, если ADO не удается определить количество записей или тип поставщика или курсора не поддерживает **RecordCount**. Чтение свойства **RecordCount** в закрытом **наборе записей** вызывает ошибку.

#### <a name="bookmarks-or-approximate-positioning"></a>Закладки или приближенное позиционирование

Если *объект Recordset* поддерживает закладки или приближенное позиционирование, это свойство возвращает точное число записей в наборе записей. Это свойство возвращает точное число, независимо от того, заполнен ли набор записей полностью.

В отличие от этого, если объект набора записей *не* поддерживает закладки или приближенное позиционирование, доступ к этому свойству может быть значительным стоком ресурсов. Сток происходит потому, что все записи должны извлекаться и подсчитываться для возврата точных значений RecordCount.

- **адбукмарк** , связанные с закладками.
- **адаппрокспоситион** относится к приблизительному размещению.

> [!NOTE]
> В ADO версии 2,8 и более ранних версиях поставщик SQLOLEDB извлекает все записи при использовании курсора на стороне сервера, несмотря на тот факт, что он возвращает **true** для обоих **поддерживаемых типов (Адаппрокспоситион)** и **поддерживает (адбукмарк)**.
  
Тип курсора объекта **Recordset** определяет, можно ли определить количество записей. Свойство **RecordCount** возвращает значение-1 для однопроходного курсора; фактическое число для курсора статического или ключевого набора ключей; и значение-1 или фактическое число для динамического курсора, в зависимости от источника данных.
  
## <a name="applies-to"></a>Применение

[Объект Recordset (ADO)](./recordset-object-ado.md)  
  
## <a name="see-also"></a>См. также:

[Пример свойств Filter и RecordCount (Visual Basic)](./filter-and-recordcount-properties-example-vb.md)   
[Пример свойств Filter и RecordCount (Visual c++)](./filter-and-recordcount-properties-example-vc.md)   
[Свойство примеры AbsolutePosition (ADO)](./absoluteposition-property-ado.md)   
[Свойство PageCount (ADO)](./pagecount-property-ado.md)