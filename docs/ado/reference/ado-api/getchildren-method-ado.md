---
description: Метод GetChildren (ADO)
title: Метод дочернего элемента (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _Record::raw_GetChildren
- _Record::GetChildren
helpviewer_keywords:
- GetChildren method [ADO]
ms.assetid: b3f09bac-4f66-49f6-aa5a-6fbb4fb28338
author: rothja
ms.author: jroth
ms.openlocfilehash: cb49de0d3613cca9d24991e67ee8787c0d863b8c
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99167284"
---
# <a name="getchildren-method-ado"></a>Метод GetChildren (ADO)
Возвращает [набор записей](./recordset-object-ado.md) , строки которого представляют дочерние элементы [записи](./record-object-ado.md)коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Set recordset = record.GetChildren  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект **Recordset** , для которого каждая строка представляет дочерний объект текущего объекта **Record** . Например, дочерние элементы **записи** , представляющей каталог, представляют собой файлы и подкаталоги, содержащиеся в родительском каталоге.  
  
## <a name="remarks"></a>Замечания  
 Поставщик определяет, какие столбцы существуют в возвращенном **наборе записей**. Например, поставщик источника документов всегда возвращает **набор записей** ресурсов.  
  
## <a name="applies-to"></a>Применение  

:::row:::
    :::column:::
        [Объект Record (ADO)](./record-object-ado.md)  
    :::column-end:::
    :::column:::
        [Объект Recordset (ADO)](./recordset-object-ado.md)  
    :::column-end:::
:::row-end:::