---
title: IClientVirtualDeviceSet2::Close
titlesuffix: SQL Server VDI reference
description: В этой статье приводятся справочные сведения о команде IClientVirtualDeviceSet2::Close.
ms.date: 08/30/2019
ms.prod: sql
ms.prod_service: backup-restore
ms.technology: backup-restore
ms.topic: reference
author: cawrites
ms.author: chadam
ms.openlocfilehash: fee9c16399ba091df1878774c38751a2d92880fb
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100347269"
---
# <a name="iclientvirtualdeviceset2close-vdi"></a>IClientVirtualDeviceSet2::Close (VDI)

[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]

Функция **Close** закрывает набор виртуальных устройств, созданный с помощью функции IClientVirtualDeviceSet2::Create. В результате высвобождаются все ресурсы, связанные с набором виртуальных устройств.

## <a name="syntax"></a>Синтаксис

```c
HRESULT IClientVirtualDeviceSet2::Close ();
```

## <a name="return-value"></a>Возвращаемое значение

|Возвращаемое значение | Объяснение |
|---|---|
| NOERROR | Возвращается при успешном закрытии набора виртуальных устройств. |
| VD_E_PROTOCOL | Действия не выполнялись, так как набор виртуальных устройств не открывался. |
| VD_E_OPEN | Устройства по-прежнему открыты. |

## <a name="remarks"></a>Remarks

Вызов функции Close является объявлением клиента о необходимости высвобождения всех ресурсов, используемых набором виртуальных устройств. Клиент должен убедиться, что перед вызовом функции Close завершены все действия с использованием буферов данных и виртуальных устройств. Функция Close делает недействительными все интерфейсы виртуальных устройств, возвращенные OpenDevice.

После возвращения вызова функции Close клиент может вызвать функцию Create для интерфейса набора виртуальных устройств. В этом случае создается новый набор виртуальных устройств для последующей операции резервного копирования или восстановления.

Если функция Close вызывается, когда открыты одно или несколько виртуальных устройств, возвращается VD_E_OPEN. В этом случае инициируется SignalAbort, чтобы при возможности обеспечить правильное завершение работы. Высвобождаются ресурсы VDI. Перед вызовом функции IClientVirtualDeviceSet2::Close клиент должен дождаться указания VD_E_CLOSE на каждом устройстве. Если клиент знает, что набор виртуальных устройств уже находится в состоянии аварийного завершения, он не должен ждать указания VD_E_CLOSE от команды GetCommand и может вызвать функцию IClientVirtualDeviceSet2::Close сразу же после завершения действия в общих буферах.

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения см. в [справке по интерфейсу виртуальных устройств SQL Server](reference-virtual-device-interface.md).