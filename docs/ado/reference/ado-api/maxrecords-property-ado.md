---
description: Свойство MaxRecords (ADO)
title: Свойство MaxRecords (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Recordset15::MaxRecords
helpviewer_keywords:
- MaxRecords property [ADO]
ms.assetid: 20c76571-8c9a-482c-a99e-726ab1d93f8b
author: rothja
ms.author: jroth
ms.openlocfilehash: ec7732203c4341840e6dcd05a9e37101b443a1df
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99170856"
---
# <a name="maxrecords-property-ado"></a>Свойство MaxRecords (ADO)
Указывает максимальное число записей, возвращаемых в [набор записей](./recordset-object-ado.md) из запроса.  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает или возвращает значение **типа Long** , указывающее максимальное число возвращаемых записей. Значение по умолчанию равно нулю (**0**), что означает отсутствие ограничения.  
  
## <a name="remarks"></a>Замечания  
 Свойство **maxRecords** используется для ограничения количества записей, возвращаемых поставщиком из источника данных. Значение по умолчанию этого свойства равно нулю. Это означает, что поставщик возвращает все запрошенные записи.  
  
 Свойство **maxRecords** доступно для чтения и записи, когда **набор записей** закрывается и только для чтения, когда он открыт.  
  
## <a name="applies-to"></a>Применение  
 [Объект Recordset (ADO)](./recordset-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример свойства MaxRecords (Visual Basic)](./maxrecords-property-example-vb.md)   
 [Пример свойства MaxRecords (Visual C++)](./maxrecords-property-example-vc.md)