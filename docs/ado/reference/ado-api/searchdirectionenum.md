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
ms.openlocfilehash: 0d3b03d203873a9d14aeecb7e44c7184dea274f3
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100040654"
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