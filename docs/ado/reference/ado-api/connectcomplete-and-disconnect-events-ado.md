---
description: События ConnectComplete и Disconnect (ADO)
title: События Коннекткомплете и Disconnect (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Disconnect
- Connection::ConnectComplete
- ConnectComplete
- Connection::Disconnect
helpviewer_keywords:
- Disconnect event [ADO]
- ConnectComplete event [ADO]
ms.assetid: 568f5252-d069-4d99-a01b-2ada87ad1304
author: rothja
ms.author: jroth
ms.openlocfilehash: 73966677eb224c2549954f80525d88ee5622dd0c
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100026572"
---
# <a name="connectcomplete-and-disconnect-events-ado"></a>События ConnectComplete и Disconnect (ADO)
Событие **коннекткомплете** вызывается после запуска соединения. Событие **Disconnect** вызывается после завершения соединения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
ConnectComplete pError, adStatus, pConnection  
Disconnect adStatus, pConnection  
```  
  
#### <a name="parameters"></a>Параметры  
 *pError*  
 Объект [ошибки](./error-object.md) . Она описывает ошибку, которая возникла, если значение *адстатус* равно **адстатусеррорсоккурред**; в противном случае он не задан.  
  
 *адстатус*  
 Значение [евентстатусенум](./eventstatusenum.md) , которое всегда возвращает **адстатусок**.  
  
 При вызове **коннекткомплете** этот параметр имеет значение **адстатусканцел** , если событие **виллконнект** запросило отмену ожидающего подключения.  
  
 Перед возвращением одного из событий задайте для этого параметра значение **адстатусунвантедевент** , чтобы предотвратить появление последующих уведомлений. Однако закрытие и повторное открытие [соединения](./connection-object-ado.md) приводит к повторному возникновению этих событий.  
  
 *пконнектион*  
 Объект **соединения** , к которому применяется это событие.  
  
## <a name="see-also"></a>См. также:  
 [Пример модели событий ADO (Visual c++)](./ado-events-model-example-vc.md)   
 [Общие сведения об обработчике событий ADO](../../guide/data/ado-event-handler-summary.md)