---
title: IServerVirtualDeviceSet2::IsSharedBuffer
titlesuffix: SQL Server VDI reference
description: В этой статье приводятся справочные сведения о команде IServerVirtualDeviceSet2::IsSharedBuffer.
ms.date: 08/30/2019
ms.prod: sql
ms.prod_service: backup-restore
ms.technology: backup-restore
ms.topic: reference
author: cawrites
ms.author: chadam
ms.openlocfilehash: 47d615bd8996d07444542549623d6849184815c0
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100347094"
---
# <a name="iservervirtualdeviceset2issharedbuffer-vdi"></a>IServerVirtualDeviceSet2::IsSharedBuffer (VDI)

[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]

Функция **IsSharedBuffer** определяет, относится ли указанный адрес буфера к одному из общих буферов, предоставленных методом AllocateBuffer.

## <a name="syntax"></a>Синтаксис

```c
HRESULT IServerVirtualDeviceSet2::IsSharedBuffer (
   LPVOID   lpBuffer
);
```

## <a name="parameters"></a>Параметры

*lpBuffer* — адрес буфера.

## <a name="return-value"></a>Возвращаемое значение

|Возвращаемое значение | Объяснение |
|---|---|
| TRUE | Буфер является общим. |
| FALSE | Буфер не входит в набор виртуальных устройств. |

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения см. в [справке по интерфейсу виртуальных устройств SQL Server](reference-virtual-device-interface.md).