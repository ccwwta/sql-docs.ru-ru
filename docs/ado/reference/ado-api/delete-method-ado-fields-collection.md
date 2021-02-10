---
description: Метод Delete (коллекция Fields ADO)
title: Метод Delete (коллекция полей ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Fields20::Delete
- Fields20::raw_Delete
helpviewer_keywords:
- Delete method [ADO]
ms.assetid: 25bedc25-c51c-4cab-96ce-930b959965d9
author: rothja
ms.author: jroth
ms.openlocfilehash: 9cfc2784e0a6019e4a3aaee68cb18c54b0e52fc3
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100034414"
---
# <a name="delete-method-ado-fields-collection"></a>Метод Delete (коллекция Fields ADO)
Удаляет объект из коллекции [полей](../../../ado/reference/ado-api/fields-collection-ado.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Fields.Delete Field  
```  
  
#### <a name="parameters"></a>Параметры  
 *Поле*  
 **Вариант** , обозначающий объект [поля](../../../ado/reference/ado-api/field-object.md) для удаления. Этот параметр может быть именем объекта **поля** или порядком расположения самого объекта **поля** .  
  
## <a name="remarks"></a>Remarks  
 Вызов метода **Fields. Delete** для открытого [набора записей](../../../ado/reference/ado-api/recordset-object-ado.md) приводит к ошибке времени выполнения.  
  
## <a name="applies-to"></a>Применение  
 [Коллекция Fields (ADO)](../../../ado/reference/ado-api/fields-collection-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Метод Delete (Коллекция параметров ADO)](../../../ado/reference/ado-api/delete-method-ado-parameters-collection.md)   
 [Метод Delete (набор записей ADO)](../../../ado/reference/ado-api/delete-method-ado-recordset.md)   
 [Метод DeleteRecord (ADO)](../../../ado/reference/ado-api/deleterecord-method-ado.md)
