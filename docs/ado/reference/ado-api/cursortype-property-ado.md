---
description: Свойство CursorType (ADO)
title: Свойство примеры CursorType (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Recordset15::CursorType
helpviewer_keywords:
- CursorType property [ADO]
ms.assetid: b62c66ca-58d5-430e-9257-eb38c65e48c2
author: rothja
ms.author: jroth
ms.openlocfilehash: 7dc8d34ccc631d9ecea19fdfceb36743adbaa5e0
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100034454"
---
# <a name="cursortype-property-ado"></a>Свойство CursorType (ADO)
Указывает тип курсора, используемого в объекте [набора записей](./recordset-object-ado.md) .  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает или возвращает значение [курсортипинум](./cursortypeenum.md) . Значение по умолчанию — **адопенфорвардонли**.  
  
## <a name="remarks"></a>Remarks  
 Используйте свойство **примеры CursorType** , чтобы указать тип курсора, который должен использоваться при открытии объекта **Recordset** .  
  
 Если свойство [CursorLocation](./cursorlocation-property-ado.md) имеет значение **адусеклиент**, то поддерживается только параметр **адопенстатик** . Если задано неподдерживаемое значение, то ошибка не будет возникать. Вместо этого будет использоваться ближайший поддерживаемый **примеры CursorType** .  
  
 Если поставщик не поддерживает запрошенный тип курсора, он может вернуть другой тип курсора. Свойство **примеры CursorType** изменится в соответствии с фактическим типом курсора, который используется при открытом объекте [набора записей](./recordset-object-ado.md) . Чтобы проверить конкретную функциональность возвращаемого курсора, используйте метод [поддерживает](./supports-method.md) . После закрытия **набора записей** свойство **примеры CursorType** возвращается к исходному значению.  
  
 На следующей диаграмме показаны функциональные возможности поставщика **(определяемые с помощью** констант методов), необходимые для каждого типа курсора.  
  
|Для набора записей этого примеры CursorType|Метод поддержки должен возвращать значение true для всех этих констант|  
|----------------------------------------|---------------------------------------------------------------------|  
|**адопенфорвардонли**|нет|  
|**adOpenKeyset**|**адбукмарк**, **адхолдрекордс**, **адмовепревиаус**, **адресинк**|  
|**adOpenDynamic**|**adMovePrevious**|  
|**adOpenStatic**|**адбукмарк**, **адхолдрекордс**, **адмовепревиаус**, **адресинк**|  
  
> [!NOTE]
>  Хотя **поддерживает**(**адупдатебатч**) значение true для динамических и последовательных курсоров, для пакетных обновлений следует использовать курсор KEYSET или static. Задайте для свойства [LockType](./locktype-property-ado.md) значение **адлоккбатчоптимистик** , а для свойства **CursorLocation** значение **адусеклиент** , чтобы включить службу курсора для OLE DB, которая необходима для пакетных обновлений.  
  
 Свойство **примеры CursorType** доступно для чтения и записи, когда **набор записей** закрывается и только для чтения, когда он открыт.  
  
> [!NOTE]
>  **Использование удаленной службы данных** При использовании объекта **набора записей** на стороне клиента свойство **примеры CursorType** может быть установлено только в **адопенстатик**.  
  
## <a name="applies-to"></a>Применение  
 [Объект Recordset (ADO)](./recordset-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Примеры свойств примеры CursorType, LockType и EditMode (Visual Basic)](./cursortype-locktype-and-editmode-properties-example-vb.md)   
 [Пример свойств примеры CursorType, LockType и EditMode (Visual c++)](./cursortype-locktype-and-editmode-properties-example-vc.md)   
 [Метод Supports](./supports-method.md)