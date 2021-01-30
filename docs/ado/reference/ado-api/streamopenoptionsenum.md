---
description: StreamOpenOptionsEnum
title: Стреамопеноптионсенум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- StreamOpenOptionsEnum
helpviewer_keywords:
- StreamOpenOptionsEnum enumeration [ADO]
ms.assetid: 85b6c57f-47ed-46ba-bd92-07882ae9e9d2
author: rothja
ms.author: jroth
ms.openlocfilehash: 5da222318b827eae05d07d7cad4a121a568d6540
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99166409"
---
# <a name="streamopenoptionsenum"></a>StreamOpenOptionsEnum
Задает параметры для открытия объекта [потока](./stream-object-ado.md) . Значения можно сочетать с операцией или.  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**adOpenStreamAsync**|1|Открывает объект **потока** в асинхронном режиме.|  
|**adOpenStreamFromRecord**|4|Определяет содержимое *исходного* параметра как уже открытый объект [Record](./record-object-ado.md) . Поведение по умолчанию состоит в том, чтобы рассматривать *источник* как URL-адрес, указывающий непосредственно на узел в древовидной структуре. Открывается поток по умолчанию, связанный с этим узлом.|  
|**adOpenStreamUnspecified**|-1|По умолчанию. Указывает открытие объекта **потока** с параметрами по умолчанию.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Эти константы не имеют эквивалентов ADO/WFC.  
  
## <a name="applies-to"></a>Применение  
 [Метод Open (объект Stream ADO)](./open-method-ado-stream.md)