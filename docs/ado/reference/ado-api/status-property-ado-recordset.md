---
description: Свойство Status (объект Recordset ADO)
title: Свойство Status (набор записей ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Recordset15::GetStatus
- Recordset15::Status
helpviewer_keywords:
- Status property [ADO Recordset]
ms.assetid: 41d70d89-880f-4850-9d17-19d9790cc8eb
author: rothja
ms.author: jroth
ms.openlocfilehash: e09b3d093f58890efd893ceb0ac204ab6ed12a46
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99170189"
---
# <a name="status-property-ado-recordset"></a>Свойство Status (объект Recordset ADO)
Указывает состояние текущей записи по отношению к пакетным обновлениям или другим массовым операциям.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает сумму одного или нескольких значений [рекордстатусенум](./recordstatusenum.md) .  
  
## <a name="remarks"></a>Замечания  
 Используйте свойство **Status** , чтобы узнать, какие изменения ожидаются для записей, измененных во время пакетного обновления. Свойство **Status** можно также использовать для просмотра состояния записей, которые не удалось выполнить в ходе выполнения операций с массовыми операциями, например при вызове методов [Resync](./resync-method.md), [UpdateBatch](./updatebatch-method.md)или [CancelBatch](./cancelbatch-method-ado.md) для объекта [набора записей](./recordset-object-ado.md) или при установке свойства [фильтра](./filter-property.md) для объекта **набора записей** в массив закладок. С помощью этого свойства можно определить, каким образом заданная запись не удалась, и устранить ее соответствующим образом.  
  
## <a name="applies-to"></a>Применение  
 [Объект Recordset (ADO)](./recordset-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример свойства Status (набор записей) (VB)](./status-property-example-recordset-vb.md)   
 [Пример свойства Status (Visual C++)](./status-property-example-vc.md)