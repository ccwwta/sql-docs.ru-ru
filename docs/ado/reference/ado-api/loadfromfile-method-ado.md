---
description: Метод LoadFromFile (ADO)
title: Метод Лоадфромфиле (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _Stream::raw_LoadFromFile
helpviewer_keywords:
- LoadFromFile method [ADO]
ms.assetid: b18d8d38-7354-4a94-b637-6ac035faa433
author: rothja
ms.author: jroth
ms.openlocfilehash: b1b3b375158bb8d296c9010caab900db4791fcec
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100041844"
---
# <a name="loadfromfile-method-ado"></a>Метод LoadFromFile (ADO)
Загружает содержимое существующего файла в [поток](./stream-object-ado.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Stream.LoadFromFileFileName  
```  
  
#### <a name="parameters"></a>Параметры  
 *FileName*  
 **Строковое** значение, содержащее имя файла, загружаемого в **поток**. Имя *файла* может содержать любой допустимый путь и имя в формате UNC. Если указанный файл не существует, возникает ошибка времени выполнения.  
  
## <a name="remarks"></a>Remarks  
 Этот метод можно использовать для загрузки содержимого локального файла в объект **потока** . Это можно использовать для передачи содержимого локального файла на сервер.  
  
 Перед вызовом **лоадфромфиле** объект **потока** должен быть уже открыт. Этот метод не изменяет привязку объекта **потока** ; Он по-прежнему будет привязан к объекту, указанному в URL-адресе или **записи** , с которой был первоначально открыт **поток** .  
  
 **Лоадфромфиле** перезаписывает текущее содержимое объекта **потока** с данными, считанными из файла. Все существующие байты в **потоке** перезаписываются содержимым файла. Все ранее существующие и оставшиеся байты после [EOS](./eos-property.md) , созданного **лоадфромфиле**, усекаются.  
  
 После вызова **лоадфромфиле** текущая координата устанавливается в начало **потока** ([позицией](./position-property-ado.md) является 0).  
  
 Поскольку 2 байта можно добавить в начало потока для кодирования, размер потока может не совпадать с размером файла, из которого он был загружен.  
  
## <a name="applies-to"></a>Применение  
 [Объект Stream (ADO)](./stream-object-ado.md)