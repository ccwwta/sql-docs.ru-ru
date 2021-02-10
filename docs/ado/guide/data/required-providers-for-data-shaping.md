---
description: Обязательные поставщики для формирования данных
title: Необходимые поставщики для формирования данных | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- providers [ADO], data shaping
- data shaping [ADO], providers required
ms.assetid: d49d48d2-ac2d-4c11-895c-5a149b444620
author: rothja
ms.author: jroth
ms.openlocfilehash: eb3d91f23666c900f59a6ffc8e6b94af9bcdb4d7
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100032536"
---
# <a name="required-providers-for-data-shaping"></a>Обязательные поставщики для формирования данных
Для формирования данных обычно требуется два поставщика. Поставщик услуг, [Служба формирования данных для OLE DB](../../../ado/guide/appendixes/microsoft-data-shaping-service-for-ole-db-ado-service-provider.md), предоставляет функциональные возможности формирования данных и поставщик данных, например поставщик OLE DB для SQL Server, предоставляет строки данных для заполнения [набора записей](../../../ado/reference/ado-api/recordset-object-ado.md)в форме.  
  
 Имя поставщика услуг (Мсдаташапе) может быть указано в качестве значения свойства [поставщика](../../../ado/reference/ado-api/provider-property-ado.md) объектов [соединения](../../../ado/reference/ado-api/connection-object-ado.md) или ключевого слова строки подключения "Provider = мсдаташапе;".  
  
 Имя поставщика данных может быть указано в качестве значения динамического свойства **поставщика данных** , которое добавляется в коллекцию [свойств](../../../ado/reference/ado-api/properties-collection-ado.md) объекта **соединения** службой формирования данных для OLE DB или ключевое слово строки подключения "**поставщик данных =** _поставщик_".  
  
 Поставщик данных не требуется, если **набор записей** не заполняется (например, как в созданном **наборе записей** , где столбцы создаются с помощью ключевого слова New). В этом случае укажите "**Data Provider =** None;".  
  
## <a name="example"></a>Пример  
  
```  
Dim cnn As New ADODB.Connection  
cnn.Provider = "MSDataShape"  
cnn.Open "Data Provider=SQLOLEDB;Integrated Security=SSPI;Database=Northwind"  
```  
  
## <a name="see-also"></a>См. также:  
 [Пример формирования данных](../../../ado/guide/data/data-shaping-example.md)   
 [Грамматика формальной фигуры](../../../ado/guide/data/formal-shape-grammar.md)   
 [Общие сведения о командах формирования данных](../../../ado/guide/data/shape-commands-in-general.md)
