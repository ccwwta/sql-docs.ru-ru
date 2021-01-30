---
description: Метод GetChunk (ADO)
title: Методического фрагмента данных (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Field20::raw_GetChunk
- Field20::GetChunk
helpviewer_keywords:
- GetChunk method [ADO]
ms.assetid: fc268e22-205b-44a3-9038-ffed51e23e10
author: rothja
ms.author: jroth
ms.openlocfilehash: 7d9e47713f3bd4d86f35cff2acac0255ed4ab5c7
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99164582"
---
# <a name="getchunk-method-ado"></a>Метод GetChunk (ADO)
Возвращает все или часть содержимого большого текстового или двоичного объекта [поля](./field-object.md) данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
variable = field.GetChunk(Size)  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает **значение типа Variant**.  
  
#### <a name="parameters"></a>Параметры  
 *Size*  
 **Длинное** выражение, равное количеству байтов или символов, которое необходимо получить.  
  
## <a name="remarks"></a>Замечания  
 Используйте метод **GetObject** для объекта **field** , чтобы получить часть или все его длинные двоичные или символьные данные. В ситуациях, когда память системы ограничена, можно использовать метод " **блока** " для обработки длинных значений в частях, а не полностью.  
  
 Данные, возвращаемые вызовом методаического **блока** , назначаются *переменной*. Если *Размер* больше остальных данных **, метод WebMethod** возвращает только оставшиеся данные без *переменной* заполнения пустыми пробелами. Если поле пустое **, метод WebMethod** возвращает значение null.  
  
 Каждый последующий вызов методаического **блока** извлекает данные, начиная с места, в **котором предыдущий вызов** метода Left был отключен. Однако если вы получаете данные из одного поля, а затем задаете или считываете значение другого поля в текущей записи, то ADO считает, что вы завершили извлечение данных из первого поля. При повторном вызове **метода WebMethod в первом** поле ADO интерпретирует вызов как новую операцию- **блок** и начинает чтение с начала данных. Доступ к полям других объектов [набора записей](./recordset-object-ado.md) , которые не являются клонами первого объекта **набора записей** , не приведет **к нарушению** операций GetObject.  
  
 Если бит **адфлдлонг** в свойстве [Attributes](./attributes-property-ado.md) объекта **field** имеет значение **true**, для этого поля можно **использовать метод GetObject** .  
  
 Если при **использовании метода GetObject** для объекта **поля** нет текущей записи, то происходит ошибка 3021 (нет текущей записи).  
  
> [!NOTE]
>  Метод **GetObject** не работает с объектами **полей** объекта [Record](./record-object-ado.md) . Она не выполняет никаких операций и выдает ошибку во время выполнения.  
  
## <a name="applies-to"></a>Применение  
 [Объект Field](./field-object.md)  
  
## <a name="see-also"></a>См. также:  
 [Примеры методов AppendChunk и-блока (Visual Basic)](./appendchunk-and-getchunk-methods-example-vb.md)   
 [Примеры методов AppendChunk и-блока (Visual c++)](./appendchunk-and-getchunk-methods-example-vc.md)   
 [Метод AppendChunk (ADO)](./appendchunk-method-ado.md)   
 [Свойство Attributes (ADO)](./attributes-property-ado.md)