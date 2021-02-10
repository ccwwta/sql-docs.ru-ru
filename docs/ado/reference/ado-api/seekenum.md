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
ms.openlocfilehash: 3286e6d6477cf18f95d95ccd494336e7a119f009
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100051455"
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