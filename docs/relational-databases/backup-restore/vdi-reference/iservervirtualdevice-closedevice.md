---
title: IServerVirtualDevice::CloseDevice
titlesuffix: SQL Server VDI reference
description: В этой статье приводятся справочные сведения о команде IServerVirtualDevice::CloseDevice.
ms.date: 08/30/2019
ms.prod: sql
ms.prod_service: backup-restore
ms.technology: backup-restore
ms.topic: reference
author: cawrites
ms.author: chadam
ms.openlocfilehash: 7034c517483a114d9b1a0be4fbf15f80fd8801dc
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100347169"
---
# <a name="iservervirtualdeviceclosedevice-vdi"></a>IServerVirtualDevice::CloseDevice (VDI)

[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]

Функция **CloseDevice** закрывает виртуальное устройство, которое было открыто с помощью функции IServerVirtualDeviceSet2::OpenDevice.

## <a name="syntax"></a>Синтаксис

```c
HRESULT IServerVirtualDevice::CloseDevice ();
```

## <a name="return-value"></a>Возвращаемое значение

|Возвращаемое значение | Объяснение |
|---|---|
| VD_E_CLOSE | Устройство уже закрыто. |
| VD_E_ABORT | Интерфейс находится в состоянии прерывания. |

## <a name="remarks"></a>Remarks

Функция CloseDevice не требуется после использования SignalAbort для принудительного аварийного завершения. Если функция CloseDevice вызывается после использования SignalAbort, не выполняется никаких действий.

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения см. в [справке по интерфейсу виртуальных устройств SQL Server](reference-virtual-device-interface.md).