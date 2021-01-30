---
description: SeekEnum
title: Сикенум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- SeekEnum
helpviewer_keywords:
- SeekEnum enumeration [ADO]
ms.assetid: f0ec0c92-8253-47c6-9a14-e5dbccbad219
author: rothja
ms.author: jroth
ms.openlocfilehash: f61e05965b1750c4f8e6b48f092eeb059d1e19d3
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99166558"
---
# <a name="seekenum"></a>SeekEnum
Указывает тип выполняемого [поиска](./seek-method.md) .  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**adSeekFirstEQ**|1|Ищет первый ключ, равный *кэйвалуес*.|  
|**адсикластек**|2|Ищет последний ключ, равный *кэйвалуес*.|  
|**адсикафтерек**|4|Ищет либо ключ, равный *кэйвалуес* , либо сразу после того, как было выполнено совпадение.|  
|**adSeekAfter**|8|Ищет ключ сразу после того, как произошло совпадение с *кэйвалуес* .|  
|**adSeekBeforeEQ**|16|Поиск либо ключа, равного *кэйвалуес*, либо непосредственно перед тем, как было выполнено совпадение.|  
|**adSeekBefore**|32|Ищет ключ непосредственно перед тем, как произошло совпадение с *кэйвалуес* .|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com. MS. WFC. Data**  
  
|Константа|  
|--------------|  
|Адоенумс. Seek. ФИРСТЕК|  
|Адоенумс. Seek. ЛАСТЕК|  
|Адоенумс. Seek. АФТЕРЕК|  
|Адоенумс. Seek. После|  
|Адоенумс. Seek. БЕФОРИК|  
|Адоенумс. Seek. до|  
  
## <a name="applies-to"></a>Применение  
 [Метод Seek](./seek-method.md)