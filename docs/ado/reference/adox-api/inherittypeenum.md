---
description: InheritTypeEnum
title: Инхериттипинум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- InheritTypeEnum
helpviewer_keywords:
- InheritTypeEnum enumeration [ADOX]
ms.assetid: c2f6ce79-c4b3-4d40-ac95-21025208f991
author: rothja
ms.author: jroth
ms.openlocfilehash: d758c78b8778d5a00c0105c8c9dcebfe40da22e3
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99164187"
---
# <a name="inherittypeenum"></a>InheritTypeEnum
Указывает, как объекты наследуют разрешения, заданные с помощью [SetPermissions](./setpermissions-method-adox.md).  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**adInheritBoth**|3|Элементы и другие контейнеры, содержащиеся в первичном объекте, наследуют эту запись.|  
|**адинхеритконтаинерс**|2|Другие контейнеры, содержащиеся в первичном объекте, наследуют эту запись.|  
|**адинхеритноне**|0|По умолчанию. Наследование не выполняется.|  
|**адинхеритнопропагате**|4|Флаги **адинхеритобжектс** и **адинхеритконтаинерс** не распространяются на унаследованную запись.|  
|**адинхеритобжектс**|1|Объекты, не являющиеся контейнерами в контейнере, наследуют разрешения.|  
  
## <a name="applies-to"></a>Применение  
 [Метод SetPermissions (ADOX)](./setpermissions-method-adox.md)