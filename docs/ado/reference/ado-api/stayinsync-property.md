---
description: Свойство StayInSync
title: StayInSync, свойство | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Recordset20::StayInSync
- Recordset20::put_StayInSync
- Recordset20::PutStayInSync
- Recordset20::get_StayInSync
- Recordset20::GetStayInSync
helpviewer_keywords:
- StayInSync property
ms.assetid: 502d69b5-dc9a-455d-b115-a03bd39a552b
author: rothja
ms.author: jroth
ms.openlocfilehash: 8e30e9f8157be0ab7644eedb51a2956b232baa56
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100020393"
---
# <a name="stayinsync-property"></a>Свойство StayInSync
Указывает, изменяется ли ссылка на базовые дочерние записи (то есть *глава*) в иерархическом объекте [Recordset](./recordset-object-ado.md) при изменении позиционирования родительской строки.  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает или возвращает **логическое** значение. По умолчанию используется значение **True**. Если **значение равно true**, глава будет обновлена, если родительский объект **Recordset** изменяет расположение строки. Если **значение равно false**, глава продолжит ссылаться на данные в предыдущей главе, несмотря на то, что родительский объект **набора записей** изменил расположение строки.  
  
## <a name="remarks"></a>Remarks  
 Это свойство применяется к иерархическим наборам записей, таким как поддерживаемые [службой формирования данных Майкрософт для OLE DB](../../guide/appendixes/microsoft-data-shaping-service-for-ole-db-ado-service-provider.md), и должны быть установлены в родительском **наборе записей** до получения дочернего **набора записей** . Это свойство упрощает навигацию по иерархическим наборам записей.  
  
## <a name="applies-to"></a>Применение  
 [Объект Recordset (ADO)](./recordset-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример свойства StayInSync (Visual Basic)](./stayinsync-property-example-vb.md)   
 [Служба формирования данных Майкрософт для OLE DB (поставщик служб ADO)](../../guide/appendixes/microsoft-data-shaping-service-for-ole-db-ado-service-provider.md)