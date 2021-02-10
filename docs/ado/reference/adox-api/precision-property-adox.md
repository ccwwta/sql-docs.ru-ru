---
description: Свойство Precision (ADOX)
title: Свойство Precision (ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _Column::put_Precision
- _Column::PutPrecision
- _Column::GetPrecision
- _Column::get_Precision
- _Column::Precision
helpviewer_keywords:
- Precision property [ADOX]
ms.assetid: 0e0ecbbf-d7de-49d4-a128-5a519ecd54ba
author: rothja
ms.author: jroth
ms.openlocfilehash: f98cc2ee59e7b3e0c873a6bc48c3234148543484
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100053902"
---
# <a name="precision-property-adox"></a>Свойство Precision (ADOX)
Указывает максимальную точность значений данных в [столбце](./column-object-adox.md).  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает и возвращает значение типа **Long** , которое является максимальной точностью значений данных в столбце, если свойство [Type](./type-property-column-adox.md) имеет числовой тип. **Точность** не учитывается для всех остальных типов данных.  
  
## <a name="remarks"></a>Remarks  
 Значение по умолчанию равно нулю (**0**).  
  
 Это свойство доступно только для чтения для объектов [столбцов](./column-object-adox.md) , уже добавленных в коллекцию.  
  
## <a name="applies-to"></a>Применение  
 [Объект Column (ADOX)](./column-object-adox.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример кода ADOX: пример свойства NumericScale и Precision (Visual Basic)](./adox-code-example-numericscale-and-precision-properties-example-vb.md)   
 [Свойство Type (Column) (ADOX)](./type-property-column-adox.md)   
 [Объект Column (ADOX)](./column-object-adox.md)