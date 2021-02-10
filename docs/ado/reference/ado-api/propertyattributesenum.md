---
description: PropertyAttributesEnum
title: Пропертяттрибутесенум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- PropertyAttributesEnum
helpviewer_keywords:
- PropertyAttributesEnum enumeration [ADO]
ms.assetid: 96a01955-a6b4-4cbf-9c73-52bcd1e9fb25
author: rothja
ms.author: jroth
ms.openlocfilehash: 694170521f4fc99d5dd9c99d15f48e7461acde09
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100040864"
---
# <a name="propertyattributesenum"></a>PropertyAttributesEnum
Задает атрибуты объекта [Property](./property-object-ado.md) .  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**адпропнотсуппортед**|0|Указывает, что свойство не поддерживается поставщиком.|  
|**адпропрекуиред**|1|Указывает, что пользователь должен указать значение этого свойства перед инициализацией источника данных.|  
|**adPropOptional**|2|Указывает, что пользователю не нужно указывать значение этого свойства перед инициализацией источника данных.|  
|**адпропреад**|512|Указывает, что пользователь может прочитать свойство.|  
|**adPropWrite**|1024|Указывает, что пользователь может задать свойство.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com. MS. WFC. Data**  
  
|Константа|  
|--------------|  
|Адоенумс. Пропертяттрибутес. NOTSUPPORTED|  
|AdoEnums.PropertyAttributes.REQUIRED|  
|Адоенумс. Пропертяттрибутес. необязательный|  
|Адоенумс. Пропертяттрибутес. READ|  
|Адоенумс. Пропертяттрибутес. WRITE|  
  
## <a name="applies-to"></a>Применение  
 [Свойство Attributes (ADO)](./attributes-property-ado.md)