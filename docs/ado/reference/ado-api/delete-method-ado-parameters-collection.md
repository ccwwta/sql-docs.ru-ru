---
description: Метод Delete (коллекция Parameters ADO)
title: Метод Delete (Коллекция параметров ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _DynaCollection::Delete
- _DynaCollection::raw_Delete
helpviewer_keywords:
- Delete method [ADO]
ms.assetid: 160c575e-df63-4ade-a2d3-5fd8f72e70cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 63b71709bd3c6f07c1dad3d7f3c471ecd267b202
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99171302"
---
# <a name="delete-method-ado-parameters-collection"></a>Метод Delete (коллекция Parameters ADO)
Удаляет объект из коллекции [параметров](../../../ado/reference/ado-api/parameters-collection-ado.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Parameters.Delete Index  
```  
  
#### <a name="parameters"></a>Параметры  
 *Index*  
 **Строковое** значение, содержащее имя объекта, который необходимо удалить, или порядковый номер (индекс) объекта в коллекции.  
  
## <a name="remarks"></a>Замечания  
 Использование метода **Delete** в коллекции позволяет удалить один из объектов в коллекции. Этот метод доступен только для коллекции **Parameters** объекта [Command](../../../ado/reference/ado-api/command-object-ado.md) . При вызове метода **Delete** необходимо использовать свойство [Name](../../../ado/reference/ado-api/name-property-ado.md) объекта [Parameter](../../../ado/reference/ado-api/parameter-object.md) или его индекс коллекции. переменная объекта не является допустимым аргументом.  
  
## <a name="applies-to"></a>Применение  
 [Коллекция Parameters (ADO)](../../../ado/reference/ado-api/parameters-collection-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Метод Delete (коллекция полей ADO)](../../../ado/reference/ado-api/delete-method-ado-fields-collection.md)   
 [Метод Delete (набор записей ADO)](../../../ado/reference/ado-api/delete-method-ado-recordset.md)   
 [Метод DeleteRecord (ADO)](../../../ado/reference/ado-api/deleterecord-method-ado.md)
