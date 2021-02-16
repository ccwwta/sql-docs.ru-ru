---
title: IClientVirtualDeviceSet2::SignalAbort
titlesuffix: SQL Server VDI reference
description: В этой статье приводятся справочные сведения о команде IClientVirtualDeviceSet2::SignalAbort.
ms.date: 08/30/2019
ms.prod: sql
ms.prod_service: backup-restore
ms.technology: backup-restore
ms.topic: reference
author: cawrites
ms.author: chadam
ms.openlocfilehash: b03452441b99cd477f0901e3868109867c66e2b7
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100347197"
---
# <a name="iclientvirtualdeviceset2signalabort-vdi"></a>IClientVirtualDeviceSet2::SignalAbort (VDI)

[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]

Функция **SignalAbort** используется для предупреждения об аварийном завершении.

## <a name="syntax"></a>Синтаксис

```c
HRESULT IClientVirtualDeviceSet2::SignalAbort ();
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода. Значение NOERROR указывает, что вызов метода завершился успешно. Ненулевое значение указывает, что произошла ошибка.

## <a name="remarks"></a>Remarks

Клиент может прервать операцию резервного копирования или восстановления в любое время. Эта подпрограмма оповещает о необходимости прекращения всех операций. Весь набор виртуальных устройств переходит в состояние прерывания. На устройства не возвращаются никакие дополнительные команды. Все незавершенные команды завершаются автоматически, возвращая ERROR_OPERATION_ABORTED в качестве кода завершения. После безопасного завершения всех необработанных операций использования буферов клиент должен вызвать IClientVirtualDeviceSet2::Close. Дополнительные сведения см. в разделе "Аварийное завершение".

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения см. в [справке по интерфейсу виртуальных устройств SQL Server](reference-virtual-device-interface.md).