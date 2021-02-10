---
description: Метод Flush (ADO)
title: Метод Flush (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _Stream::Flush
- _Stream::raw_Flush
helpviewer_keywords:
- Flush method [ADO]
ms.assetid: 938522b4-f836-4c80-8d27-a598a000f0ee
author: rothja
ms.author: jroth
ms.openlocfilehash: c4df6f318afaed7bbbc7a3302be2b1c6a15a5c1d
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100033962"
---
# <a name="flush-method-ado"></a>Метод Flush (ADO)
Принудительно применяет содержимое [потока](./stream-object-ado.md) , остающегося в буфере ADO, к базовому объекту, с которым связан **поток** .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Stream.Flush  
```  
  
## <a name="remarks"></a>Remarks  
 Этот метод можно использовать для отправки содержимого буфера потока в базовый объект: например, узел или файл, представленный URL-адресом, который является источником объекта **потока** . Этот метод следует вызывать, если необходимо обеспечить запись всех изменений, внесенных в содержимое **потока** . Однако при использовании ADO обычно не требуется вызывать **Сброс**, так как ADO постоянно очищает свой буфер в фоновом режиме. Изменения содержимого **потока** вносятся автоматически, а не кэшируются до вызова метода **flush** .  
  
 При закрытии **потока** с помощью метода [Close](./close-method-ado.md) содержимое **потока** автоматически очищается. нет необходимости явно вызывать метод **flush** непосредственно перед **закрытием**.  
  
## <a name="applies-to"></a>Применение  
 [Объект Stream (ADO)](./stream-object-ado.md)