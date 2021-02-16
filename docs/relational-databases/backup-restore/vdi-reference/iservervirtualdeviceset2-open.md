---
title: IServerVirtualDeviceSet2::Open
titlesuffix: SQL Server VDI reference
description: В этой статье приводятся справочные сведения о команде IServerVirtualDeviceSet2::Open.
ms.date: 08/30/2019
ms.prod: sql
ms.prod_service: backup-restore
ms.technology: backup-restore
ms.topic: reference
author: cawrites
ms.author: chadam
ms.openlocfilehash: bb5341a03ee64b3b9d1d23508e1e59048f843b35
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100347079"
---
# <a name="iservervirtualdeviceset2open-vdi"></a>IServerVirtualDeviceSet2::Open (VDI)

[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]

Функция **Open** открывает набор виртуальных устройств на сервере и должна быть первой функцией, вызываемой с помощью дескриптора интерфейса, предоставленного моделью COM.

## <a name="syntax"></a>Синтаксис

```c
HRESULT IServerVirtualDeviceSet2::Open (
   LPCWSTR      lpInstanceName,
   LPCWSTR      lpName
);
```

## <a name="parameters"></a>Параметры

*lpInstanceName* — эта строка определяет экземпляр SQL Server, в который будет отправлена команда SQL. Значение NULL означает экземпляр по умолчанию на текущем компьютере.

*lpName* — предоставляется из первого предложения VIRTUAL_DEVICE= команды резервного копирования или восстановления. Это имя используется в качестве ключа для получения доступа к набору виртуальных устройств, созданному клиентом.

## <a name="return-value"></a>Возвращаемое значение

|Возвращаемое значение | Объяснение |
|---|---|
| NOERROR | Функция выполнена успешно. |
| VD_E_INVALID | Указанное имя не принадлежит набору виртуальных устройств, доступному для сервера. |

## <a name="remarks"></a>Remarks

После успешного вызова этой функции сервер может настроить набор виртуальных устройств с помощью GetConfiguration и SetConfiguration.

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения см. в [справке по интерфейсу виртуальных устройств SQL Server](reference-virtual-device-interface.md).