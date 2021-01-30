---
description: Команда SET BLOCKSIZE
title: Команда установки блока размерности | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- set blocksize command [ODBC]
ms.assetid: 0c11580f-37f5-4a8e-99be-9fb9c44bb433
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: f1777b62d279db78154383a3f328591776c0a5c5
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99208657"
---
# <a name="set-blocksize-command"></a>Команда SET BLOCKSIZE
Указывает, как выделяется место на диске для хранения полей MEMO.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
SET BLOCKSIZE TO nBytes  
```  
  
## <a name="arguments"></a>Аргументы  
 *nBytes*  
 Указывает размер блока, в котором выделяется место на диске для полей MEMO. Если *nBytes* имеет значение 0, место на диске выделяется в виде одного байта (блоков из 1 байта). Если *nBytes* представляет собой целое число от 1 до 32, то место на диске выделяется в блоках из *nBytes* байт, умноженных на 512. Если *nBytes* больше 32, то место на диске выделяется в блоках *nBytes* байт. Если задать значение размера блока, превышающее 32, можно сэкономить место на диске.  
  
## <a name="remarks"></a>Замечания  
 Значение по умолчанию для SET размер блока — 64. Чтобы сбросить размер блока до другого значения после создания файла, присвойте ему новое значение, а затем используйте COPY для создания новой таблицы. Новая таблица имеет указанный размер блока.
