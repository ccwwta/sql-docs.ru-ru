---
title: IServerVirtualDeviceSet2::OpenDevice
titlesuffix: SQL Server VDI reference
description: В этой статье приводятся справочные сведения о команде IServerVirtualDeviceSet2::OpenDevice.
ms.date: 08/30/2019
ms.prod: sql
ms.prod_service: backup-restore
ms.technology: backup-restore
ms.topic: reference
author: cawrites
ms.author: chadam
ms.openlocfilehash: d0da9263463fbe6c875bc411f88ec7f8ab440f46
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100347069"
---
# <a name="iservervirtualdeviceset2opendevice-vdi"></a>IServerVirtualDeviceSet2::OpenDevice (VDI)

[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]

Функция **OpenDevice** получает интерфейсы виртуальных устройств из набора виртуальных устройств.

## <a name="syntax"></a>Синтаксис

```c
HRESULT IServerVirtualDeviceSet2::OpenDevice (
   LPCWSTR                     lpName,
   IServerVirtualDevice**      ppVirtualDevice
);
```

## <a name="parameters"></a>Параметры

*lpName* — предоставляется из первого предложения VIRTUAL_DEVICE= команды резервного копирования или восстановления. Это имя используется в качестве ключа для получения доступа к набору виртуальных устройств, созданному клиентом.

*ppVirtualDevice* — используется для возврата интерфейса виртуального устройства.

## <a name="return-value"></a>Возвращаемое значение

|Возвращаемое значение | Объяснение |
|---|---|
| NOERROR | Функция выполнена успешно. |
| VD_E_OPEN |Все устройства открыты. |

## <a name="remarks"></a>Remarks

Каждый вызов возвращает следующее не открытое устройство. Функцию можно вызвать столько раз, сколько устройств указано в конфигурации набора виртуальных устройств.

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения см. в [справке по интерфейсу виртуальных устройств SQL Server](reference-virtual-device-interface.md).