---
description: Свойство AbsolutePosition (ADO)
title: Свойство примеры AbsolutePosition (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Recordset15::AbsolutePosition
helpviewer_keywords:
- AbsolutePosition property [ADO]
ms.assetid: 79f8ee5e-fc70-46d8-8c29-ebf943c66592
author: rothja
ms.author: jroth
ms.openlocfilehash: b394ab30d4ee8d73e879abe2687e1208ba3188ad
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99161015"
---
# <a name="absoluteposition-property-ado"></a>Свойство AbsolutePosition (ADO)
Указывает порядковый номер текущей записи объекта [набора записей](./recordset-object-ado.md) .  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Для 32-разрядного кода задает или возвращает значение **типа Long** от 1 до числа записей в объекте **набора записей** ([RecordCount](./recordcount-property-ado.md)) или возвращает одно из значений [поситионенум](./positionenum.md) .  
  
 Для 64-разрядного кода используйте тип данных, который обеспечивает хранение 64-разрядного значения. Например, можно использовать либо длинное, либо другое значение, равное 64-разрядной длине, например ДБОРДИНАЛ. Не используйте значения **поситионенум** , так как они ограничены 32-разрядной длиной.  
  
## <a name="remarks"></a>Замечания  
 Чтобы задать свойство **примеры AbsolutePosition** , для ADO требуется, чтобы поставщик OLE DB использовал интерфейс [IRowsetLocate: IRowset](/previous-versions/windows/desktop/ms721190(v=vs.85)) .  
  
 При доступе к свойству **примеры AbsolutePosition** **набора записей** , открытого с помощью однопроходного или динамического курсора, возникает ошибка **адеррфеатуренотаваилабле**. При использовании других типов курсоров правильное расположение будет возвращено, пока поставщик OLE DB поддерживает интерфейс **IRowsetScroll: IRowsetLocate** . Если поставщик не поддерживает интерфейс **IRowsetScroll** , для свойства задается значение **адпосункновн**. Обратитесь к документации поставщика, чтобы определить, поддерживает ли он **IRowsetScroll**.  
  
 Используйте свойство **примеры AbsolutePosition** для перехода к записи на основе ее порядкового положения в объекте **набора записей** или для определения порядкового номера текущей записи. Чтобы это свойство было доступно, поставщик должен поддерживать соответствующие функциональные возможности.  
  
 Как и свойство [примеры absolutepage](./absolutepage-property-ado.md) , **примеры AbsolutePosition** является 1 и равно 1, если текущая запись является первой записью в **наборе записей**. Можно получить общее число записей в объекте **набора записей** из свойства [RecordCount](./recordcount-property-ado.md) .  
  
 Если задать свойство **примеры AbsolutePosition** , даже если оно относится к записи в текущем КЭШЕ, ADO перезагружает кэш с новой группой записей, начиная с указанной записи. Свойство [CacheSize](./cachesize-property-ado.md) определяет размер этой группы.  
  
> [!NOTE]
>  Не следует использовать свойство **примеры AbsolutePosition** в качестве номера суррогатной записи. При удалении предыдущей записи изменяется ее расположение. Также нет гарантии того, что данная запись будет иметь тот же **примеры AbsolutePosition** при повторном запросе или открытии объекта **набора записей** . Закладки по-прежнему являются рекомендуемым способом удержания и возврата в заданную позицию и являются единственным способом позиционирования всех типов объектов **набора записей** .  
  
## <a name="applies-to"></a>Применение  
 [Объект Recordset (ADO)](./recordset-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Примеры свойств примеры AbsolutePosition и CursorLocation (Visual Basic)](./absoluteposition-and-cursorlocation-properties-example-vb.md)   
 [Пример свойств примеры AbsolutePosition и CursorLocation (Visual c++)](./absoluteposition-and-cursorlocation-properties-example-vc.md)   
 [Свойство примеры absolutepage (ADO)](./absolutepage-property-ado.md)   
 [Свойство RecordCount (ADO)](./recordcount-property-ado.md)