---
description: Свойство DataMember
title: Свойство DataMember | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Recordset20::DataMember
helpviewer_keywords:
- DataMember property
ms.assetid: 2c8fb09e-10ad-49b5-ab41-2603771780d9
author: rothja
ms.author: jroth
ms.openlocfilehash: 1026951122336e67760f74077044ff5fd9b9fd76
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100034434"
---
# <a name="datamember-property"></a>Свойство DataMember
Указывает имя элемента данных, который будет извлечен из [набора записей](../../../ado/reference/ado-api/recordset-object-ado.md) , на который ссылается свойство [DataSource](../../../ado/reference/ado-api/datasource-property-ado.md) .  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает или возвращает **строковое** значение. Имя без учета регистра.  
  
## <a name="remarks"></a>Remarks  
 Это свойство используется для создания элементов управления с привязкой к данным в среде данных. Среда данных хранит коллекции данных (источники данных), содержащие именованные объекты (элементы данных), которые будут представлены в виде объекта [набора записей](../../../ado/reference/ado-api/recordset-object-ado.md) .  
  
 Свойства **DataMember** и **DataSource** должны использоваться вместе.  
  
 Свойство **DataMember** определяет, какой объект, заданный свойством **DataSource** , будет представлен как объект **набора записей** . Перед установкой этого свойства объект **набора записей** должен быть закрыт. Если свойство **DataMember** не задано перед свойством **DataSource** или если имя **DataMember** не распознается объектом, указанным в свойстве **DataSource** , возникает ошибка.  
  
## <a name="usage"></a>Использование  
  
```  
Dim rs as New ADODB.Recordset  
rs.DataMember = "Command"     'Name of the rowset to bind to  
Set rs.DataSource = myDE      'Name of the object containing an IRowset  
```  
  
## <a name="applies-to"></a>Применение  
 [Объект Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Свойство DataSource (ADO)](../../../ado/reference/ado-api/datasource-property-ado.md)
