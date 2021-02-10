---
description: ParameterDirectionEnum
title: Параметердиректионенум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- ParameterDirectionEnum
helpviewer_keywords:
- ParameterDirectionEnum enumeration [ADO]
ms.assetid: c66aa6e6-d4f0-4f0f-9640-e08ae6cfdef3
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b352c5504571d50e8840e0d05e0d906a07d4b36
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100041124"
---
# <a name="parameterdirectionenum"></a>ParameterDirectionEnum
Указывает, представляет ли [параметр](./parameter-object.md) входной параметр, выходной параметр, как входной, так и выходной параметр, или возвращаемое значение из хранимой процедуры.  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**адпараминпут**|1|По умолчанию. Указывает, что параметр представляет входной параметр.|  
|**адпараминпутаутпут**|3|Указывает, что параметр представляет как входной, так и выходной параметр.|  
|**адпарамаутпут**|2|Указывает, что параметр представляет выходной параметр.|  
|**адпарамретурнвалуе**|4|Указывает, что параметр представляет возвращаемое значение.|  
|**адпарамункновн**|0|Указывает, что направление параметра неизвестно.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com. MS. WFC. Data**  
  
|Константа|  
|--------------|  
|Адоенумс. Параметердиректион. INPUT|  
|Адоенумс. Параметердиректион. ИНПУТАУТПУТ|  
|Адоенумс. Параметердиректион. OUTPUT|  
|Адоенумс. Параметердиректион. RETURNVALUE|  
|Адоенумс. Параметердиректион. UNKNOWN|  
  
## <a name="applies-to"></a>Применение  

:::row:::
    :::column:::
        [Метод CreateParameter (ADO)](./createparameter-method-ado.md)  
    :::column-end:::
    :::column:::
        [Свойство Direction](./direction-property.md)  
    :::column-end:::
:::row-end:::