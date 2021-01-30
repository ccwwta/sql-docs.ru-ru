---
description: Коллекция Fields (ADO)
title: Коллекция Fields (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Fields
- Recordset15::Fields
- _Record::Fields
helpviewer_keywords:
- Fields collection [ADO]
ms.assetid: 7c371474-b88f-4730-afa5-44163a0488d5
author: rothja
ms.author: jroth
ms.openlocfilehash: 2e16bf602bd0c54b425587fcf1a50d2cc60b2aa7
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99167362"
---
# <a name="fields-collection-ado"></a>Коллекция Fields (ADO)
Содержит все объекты [полей](./field-object.md) [набора записей](./recordset-object-ado.md) или объекта [записи](./record-object-ado.md) .  
  
## <a name="remarks"></a>Замечания  
 Объект **набора записей** содержит коллекцию **Fields** , состоящие из объектов **полей** . Каждый объект **field** соответствует столбцу в **наборе записей**. Можно заполнить коллекцию **Fields** перед открытием **набора записей** , вызвав метод [Refresh](./refresh-method-ado.md) в коллекции.  
  
> [!NOTE]
>  Более подробное описание использования объектов **полей** см. в разделе объект **поля** .  
  
 Коллекция **Fields** имеет метод [append](./append-method-ado.md) , который подготавливает создание и добавление объекта **field** в коллекцию, и метод **Update** , который завершает любые добавления или удаления.  
  
 Объект **Record** имеет два специальных поля, которые можно индексировать с помощью констант [фиелденум](./fieldenum.md) . Одна константа обращается к полю, содержащему поток по умолчанию для **записи**, а другой — к полю, содержащему абсолютную строку URL-адреса для **записи**.  
  
 Некоторые поставщики (например, [поставщик Microsoft OLE DB для публикации в Интернете](../../guide/appendixes/microsoft-ole-db-provider-for-internet-publishing.md)) могут заполнить коллекцию **Fields** набором доступных полей для **записи** или **набора записей**. Другие поля не добавляются в коллекцию до тех пор, пока на них не будет первая ссылка по имени или индексу в коде.  
  
 При попытке сослаться на несуществующее поле по имени новый объект **field** будет добавлен в коллекцию **Fields** с [состоянием](./status-property-ado-field.md) **адфиелдпендингинсерт**. При вызове [Update](./update-method.md)объект ADO создает новое поле в источнике данных, если оно разрешено поставщиком.  
  
 Этот раздел содержит следующий раздел.  
  
-   [Свойства, методы и события коллекции Fields](./fields-collection-properties-methods-and-events.md)  
  
## <a name="see-also"></a>См. также:  
 [Объект Field](./field-object.md)