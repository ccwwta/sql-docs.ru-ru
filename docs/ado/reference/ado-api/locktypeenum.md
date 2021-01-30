---
description: LockTypeEnum
title: Локктипинум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- LockTypeEnum
helpviewer_keywords:
- LockTypeEnum enumeration [ADO]
ms.assetid: d2894eaf-4450-4ace-aa51-c8b875fd3010
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ad4c3b690592621fbbb243be6fcb06ce4f362be
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99167153"
---
# <a name="locktypeenum"></a>LockTypeEnum
Указывает тип блокировки, помещаемой в записи во время редактирования.  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**адлоккбатчоптимистик**|4|Обозначает обновления оптимистических пакетов. Требуется для режима пакетного обновления.|  
|**adLockOptimistic**|3|Обозначает оптимистичную блокировку, запись по записям. Поставщик использует оптимистичную блокировку, блокируя записи только при вызове метода [Update](./update-method.md) .|  
|**адлоккпессимистик**|2|Указывает пессимистическую блокировку, запись по записям. Поставщик выполняет необходимые действия, чтобы обеспечить успешное редактирование записей, обычно путем блокировки записей в источнике данных сразу после редактирования.|  
|**адлоккреадонли**|1|Указывает записи, которые доступны только для чтения. Изменить данные нельзя.|  
|**адлоккунспеЦифиед**|-1|Не указывает тип блокировки. Для клонов создается клон с тем же типом блокировки, что и у оригинала.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com. MS. WFC. Data**  
  
|Константа|  
|--------------|  
|AdoEnums.LockType.BATЧОПТИМИСТИК|  
|Адоенумс. LockType. ОПТИМИСТИЧный|  
|Адоенумс. LockType. ПЕССИМИСТическая|  
|Адоенумс. LockType. READONLY|  
|Адоенумс. LockType. не указано|  
  
## <a name="applies-to"></a>Применение  

:::row:::
    :::column:::
        [Метод Clone (ADO)](./clone-method-ado.md)  
        [Свойство LockType (ADO)](./locktype-property-ado.md)  
    :::column-end:::
    :::column:::
        [Метод Open (объект Recordset ADO)](./open-method-ado-recordset.md)  
        [Событие WillExecute (ADO)](./willexecute-event-ado.md)  
    :::column-end:::
:::row-end:::