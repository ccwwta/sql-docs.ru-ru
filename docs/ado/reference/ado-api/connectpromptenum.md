---
description: ConnectPromptEnum
title: Коннектпромптенум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- ConnectPromptEnum
helpviewer_keywords:
- ConnectPromptEnum enumeration [ADO]
ms.assetid: 21026e24-62b7-4cc9-8aef-62c1fc6cba75
author: rothja
ms.author: jroth
ms.openlocfilehash: 98a4e0d65ffb0596825557813cf12266b9fe79ed
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100034624"
---
# <a name="connectpromptenum"></a>ConnectPromptEnum
Указывает, должно ли отображаться диалоговое окно для запроса отсутствующих параметров при открытии соединения с источником данных.  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**адпромпталвайс**|1|Всегда запрашивает.|  
|**adPromptComplete**|2|Запрашивает, требуется ли дополнительная информация.|  
|**adPromptCompleteRequired**|3|Запрашивает дополнительные сведения, но необязательные параметры не допускаются.|  
|**adPromptNever**|4|Никогда не запрашивается.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com. MS. WFC. Data**  
  
|Константа|  
|--------------|  
|Адоенумс. Коннектпромпт. ALWAYS|  
|Адоенумс. Коннектпромпт. COMPLETE|  
|Адоенумс. Коннектпромпт. КОМПЛЕТЕРЕКУИРЕД|  
|Адоенумс. Коннектпромпт. NEVER|  
  
## <a name="applies-to"></a>Применение  
 [Свойство Prompt (динамическое) (ADO)](./prompt-property-dynamic-ado.md)