---
description: ADCPROP_ASYNCTHREADPRIORITY_ENUM
title: ADCPROP_ASYNCTHREADPRIORITY_ENUM | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- ADCPROP_ASYNCTHREADPRIORITY_ENUM
helpviewer_keywords:
- ADCPROP_ASYNCTHREADPRIORITY_ENUM [ADO]
ms.assetid: f0965617-17d8-41e0-98d0-f824274735a6
author: rothja
ms.author: jroth
ms.openlocfilehash: ff25342a8ba7976b883ecdca8e55f8695bf45099
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100031476"
---
# <a name="adcprop_asyncthreadpriority_enum"></a>ADCPROP_ASYNCTHREADPRIORITY_ENUM
Для объекта [RECORDSET](./recordset-object-ado.md) RDS указывает приоритет выполнения асинхронного потока, который получает данные.  
  
 Используйте эти константы с динамическим свойством " **набор записей** "**приоритета фонового потока**", которое указывается в индексе динамического свойства ADO-to-OLE DB и описано в [службе курсора Майкрософт для OLE DBной](../../guide/appendixes/microsoft-cursor-service-for-ole-db-ado-service-component.md) документации.  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**адприоритябовенормал**|4|Устанавливает приоритет между обычным и высшим.|  
|**адприоритибеловнормал**|2|Устанавливает приоритет между наименьшим и нормальным.|  
|**адприоритихигхест**|5|Устанавливает приоритет максимально возможного.|  
|**адприоритиловест**|1|Устанавливает для приоритета наименьшее возможное значение.|  
|**адприоритинормал**|3|Задает для приоритета значение Обычная.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com. MS. WFC. Data**  
  
|Константа|  
|--------------|  
|Адоенумс. Адкпропасинксреадприорити. ABOVENORMAL|  
|Адоенумс. Адкпропасинксреадприорити. BELOWNORMAL|  
|Адоенумс. Адкпропасинксреадприорити. ВЫСШИй|  
|Адоенумс. Адкпропасинксреадприорити. НИЗШИй|  
|Адоенумс. Адкпропасинксреадприорити. Обычная|