---
description: ResyncEnum
title: Ресинценум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- ResyncEnum
helpviewer_keywords:
- ResyncEnum enumeration [ADO]
ms.assetid: d3df2c90-e570-4c40-a79a-25b3448a009c
author: rothja
ms.author: jroth
ms.openlocfilehash: db02c56f55b577c9f74a42f43abc9a1957311c0d
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100040754"
---
# <a name="resyncenum"></a>ResyncEnum
Указывает, перезаписываются ли базовые значения при вызове повторной [синхронизации](./resync-method.md).  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**адресинкаллвалуес**|2|По умолчанию. Перезаписывает данные, и ожидающие обновления отменяются.|  
|**адресинкундерлингвалуес**|1|Не перезаписывает данные, а ожидающие обновления не отменяются.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com. MS. WFC. Data**  
  
|Константа|  
|--------------|  
|Адоенумс. Resync. В ALLVALUES|  
|Адоенумс. Resync. УНДЕРЛИНГВАЛУЕС|  
  
## <a name="applies-to"></a>Применение  
 [Метод Resync](./resync-method.md)