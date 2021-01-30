---
description: ConnectOptionEnum
title: Коннектоптионенум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- ConnectOptionEnum
helpviewer_keywords:
- ConnectOptionEnum enumeration [ADO]
ms.assetid: bff07eeb-dee3-4e4e-9b2d-d56061ea744d
author: rothja
ms.author: jroth
ms.openlocfilehash: 257dd82d5740c89fd8ca9f8f8d1969d27b9301ba
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99171432"
---
# <a name="connectoptionenum"></a>ConnectOptionEnum
Указывает, должен ли метод [открытия](./open-method-ado-connection.md) объекта [соединения](./connection-object-ado.md) возвращаться после установления соединения (синхронно) или до (асинхронно).  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**adAsyncConnect**|16|Асинхронно открывает подключение. Для определения доступности подключения можно использовать событие [коннекткомплете](./connectcomplete-and-disconnect-events-ado.md) .|  
|**adConnectUnspecified**|-1|По умолчанию. Синхронно открывает подключение.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com. MS. WFC. Data**  
  
|Константа|  
|--------------|  
|AdoEnums.ConnectOption.ASYNCCONNECT|  
|Адоенумс. Коннектоптион. КОННЕКТУНСПЕЦИФИЕД|  
  
## <a name="applies-to"></a>Применение  
 [Метод Open (объект Connection ADO)](./open-method-ado-connection.md)