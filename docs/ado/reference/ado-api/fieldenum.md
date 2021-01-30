---
description: FieldEnum
title: Фиелденум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- FieldEnum
helpviewer_keywords:
- FieldEnum enumeration [ADO]
ms.assetid: be4eda13-d4e4-4d6b-bb0d-3310b0a96fc2
author: rothja
ms.author: jroth
ms.openlocfilehash: 7a6975e606544ddc05a838fa0238d95132c13bf1
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99171075"
---
# <a name="fieldenum"></a>FieldEnum
Задает специальные поля, на которые ссылается коллекция [Fields](./fields-collection-ado.md) объекта [Record](./record-object-ado.md) .  
  
## <a name="remarks"></a>Замечания  
 Эти константы предоставляют "ярлык" для доступа к специальным полям, связанным с **записью**. Получите объект [поля](./field-object.md) из коллекции **полей** , а затем получите его содержимое со свойством [value](./value-property-ado.md) объекта **field** .  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**аддефаултстреам**|-1|Ссылается на поле, содержащее объект [потока](./stream-object-ado.md) по умолчанию, связанный с **записью**.|  
|**adRecordURL**|-2|Ссылается на поле, содержащее абсолютную строку URL-адреса для текущей **записи**.|