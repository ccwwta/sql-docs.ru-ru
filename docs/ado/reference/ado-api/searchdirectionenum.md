---
description: SearchDirectionEnum
title: Сеарчдиректионенум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- SearchDirectionEnum
helpviewer_keywords:
- SearchDirectionEnum enumeration [ADO]
ms.assetid: 81272ae3-2165-4f4e-adfe-9ede0368cb17
author: rothja
ms.author: jroth
ms.openlocfilehash: 957e84b3a98f0248e41a83301ef2c9a9c1943b11
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99166582"
---
# <a name="searchdirectionenum"></a>SearchDirectionEnum
Указывает направление поиска записей в [наборе записей](./recordset-object-ado.md).  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**adSearchBackward**|-1|Поиск в обратном направлении, остановка в начале **набора записей**. Если совпадение не найдено, указатель записи размещается по адресу [BOF](./bof-eof-properties-ado.md).|  
|**adSearchForward**|1|Поиск вперед, остановка в конце **набора записей**. Если совпадение не найдено, указатель записи размещается на [EOF](./bof-eof-properties-ado.md).|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com. MS. WFC. Data**  
  
|Константа|  
|--------------|  
|Адоенумс. Сеарчдиректион. назад|  
|Адоенумс. Сеарчдиректион. FORWARD|  
  
## <a name="applies-to"></a>Применение  
 [Метод Find (ADO)](./find-method-ado.md)