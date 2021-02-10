---
description: Событие onReadyStateChange (служба удаленных рабочих столов)
title: Событие onReadyStateChange (RDS) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
helpviewer_keywords:
- onReadyStateChange event [ADO]
ms.assetid: bf2ae3ac-bfe4-4709-b50a-ea7c282c3164
author: rothja
ms.author: jroth
ms.openlocfilehash: b986f3afce40bf5b114a06cc152c1dd026857859
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100049294"
---
# <a name="onreadystatechange-event-rds"></a>Событие onReadyStateChange (служба удаленных рабочих столов)
Событие **onReadyStateChange** вызывается при каждом изменении значения свойства [ReadyState](./readystate-property-rds.md) .  
  
> [!IMPORTANT]
>  Начиная с Windows 8 и Windows Server 2012, компоненты RDS больше не включены в операционную систему Windows (Дополнительные сведения см. в статье о совместимости Windows 8 и [Windows server 2012 Cookbook](https://www.microsoft.com/download/details.aspx?id=27416) ). Клиентские компоненты RDS будут удалены в следующей версии Windows. Избегайте использования этого компонента в новых разработках и запланируйте изменение существующих приложений, в которых он применяется. Приложения, использующие RDS, должны переноситься в [службу данных WCF](/dotnet/framework/wcf/).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
onReadyStateChange  
```  
  
#### <a name="parameters"></a>Параметры  
 Нет.  
  
## <a name="remarks"></a>Remarks  
 Свойство **ReadyState** отражает ход выполнения [RDS. Объект «элемент управления](./datacontrol-object-rds.md) данными» асинхронно извлекает данные в объект [набора записей](../ado-api/recordset-object-ado.md) . Используйте событие **onReadyStateChange** для отслеживания изменений в свойстве **ReadyState** при каждом возникновении. Это более эффективно, чем периодическая проверка значения свойства.  
  
## <a name="applies-to"></a>Применение  
 [Объект DataControl (служба удаленных рабочих столов)](./datacontrol-object-rds.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример модели событий ADO (Visual c++)](../ado-api/ado-events-model-example-vc.md)   
 [Общие сведения об обработчике событий ADO](../../guide/data/ado-event-handler-summary.md)