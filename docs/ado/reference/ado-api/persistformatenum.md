---
description: PersistFormatEnum
title: Персистформатенум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- PersistFormatEnum
helpviewer_keywords:
- PersistFormatEnum enumeration [ADO]
ms.assetid: ebe1a2ab-e9f1-43a2-8f94-b190c9613d70
author: rothja
ms.author: jroth
ms.openlocfilehash: 0d5968d9193f8e083982703664abf29ade2c864c
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100041024"
---
# <a name="persistformatenum"></a>PersistFormatEnum
Задает формат, в котором сохраняется [набор записей](./recordset-object-ado.md).  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**adPersistADTG**|0|Указывает формат Microsoft Advanced Data Таблеграм (АДТГ).|  
|**adPersistADO**|1|Указывает, что будет использоваться собственный формат язык XML ADO (XML). Это значение совпадает с Адперсистксмл и включено для обеспечения обратной совместимости.|  
|**adPersistXML**|1|Указывает формат язык XML (XML).|  
|**adPersistProviderSpecific**|2|Указывает, что поставщик будет сохранять **набор записей** в собственном формате.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com. MS. WFC. Data**  
  
|Константа|  
|--------------|  
|AdoEnums.PersistFormat.ADTG|  
|AdoEnums.PersistFormat.XML|  
  
## <a name="applies-to"></a>Применение  
 [Метод Save](./save-method.md)