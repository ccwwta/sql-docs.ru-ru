---
title: IClientVirtualDeviceSet2::MapBufferHandle
titlesuffix: SQL Server VDI reference
description: В этой статье приводятся справочные сведения о команде IClientVirtualDeviceSet2::MapBufferHandle.
ms.date: 08/30/2019
ms.prod: sql
ms.prod_service: backup-restore
ms.technology: backup-restore
ms.topic: reference
author: cawrites
ms.author: chadam
ms.openlocfilehash: 28ce82433b718bc98c6a27e66385b97996fe65a0
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100347226"
---
# <a name="iclientvirtualdeviceset2mapbufferhandle-vdi"></a>IClientVirtualDeviceSet2::MapBufferHandle (VDI)

[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]

Функция **MapBufferHandle** используется для получения допустимого адреса буфера из дескриптора буфера, полученного из другого процесса.

## <a name="syntax"></a>Синтаксис

```c
HRESULT IClientVirtualDeviceSet2::MapBufferHandle (
   DWORD      dwBuffer,
   BYTE**      ppBuffer
);
```

## <a name="parameters"></a>Параметры

*dwBuffer* — это дескриптор, возвращаемый функцией IClientVirtualDeviceSet2::GetBufferHandle.

*ppBuffer* — это адрес буфера, допустимый в текущем процессе.

## <a name="return-value"></a>Возвращаемое значение

|Возвращаемое значение | Объяснение |
|---|---|
| NOERROR | Функция выполнена успешно. |
| VD_E_PROTOCOL | Набор виртуальных устройств в настоящее время не открыт. |
| VD_E_INVALID | ppBuffer является недопустимым дескриптором. |

## <a name="remarks"></a>Remarks

Необходимо правильно передавать данные о дескрипторах. Дескрипторы являются локальными по отношению к одному набору виртуальных устройств. Партнерские процессы с общим дескриптором должны гарантировать использование дескрипторов буферов только в пределах набора виртуальных устройств, из которого буфер был получен изначально.

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения см. в [справке по интерфейсу виртуальных устройств SQL Server](reference-virtual-device-interface.md).