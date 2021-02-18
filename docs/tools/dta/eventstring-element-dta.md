---
title: Элемент EventString (DTA)
description: В служебной программе dta элемент EventString указывает рабочую нагрузку скрипта Transact-SQL непосредственно во входном XML-файле.
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- EventString element
ms.assetid: f76c37b4-2f6e-4274-8ee2-87e89d98e8a2
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.custom: seo-lt-2019
ms.date: 03/14/2017
ms.openlocfilehash: b2b19cee883683043893e59da2ca6ddcb5f3456a
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100335995"
---
# <a name="eventstring-element-dta"></a>Элемент EventString (DTA)

 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

Задает скрипт рабочей нагрузки [!INCLUDE[tsql](../../includes/tsql-md.md)] непосредственно во входном XML-файле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
<Workload>  
    <EventString Weight="...">  
    ...code removed here...  
    </EventString>  
</Workload>  
```  
  
## <a name="element-attributes"></a>Атрибуты элемента  
  
|attribute|Описание|  
|---------------|-----------------|  
|**Weight**|Необязательный параметр. Задает весовой коэффициент запроса (коэффициент важности) для указанного события. Для указания весового коэффициента используется тип данных **float** . Например, **Weight**="100.01". Минимальное значение, которое можно задать для коэффициента **Weight** , равно 0.|  
  
## <a name="element-characteristics"></a>Характеристики элемента  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|**Тип данных и длина**|**string**, неограниченная длина|  
|**Значение по умолчанию**|Нет.|  
|**Наличие**|Необходимо наличие одного такого элемента, если не задан никакой другой тип рабочей нагрузки. Для родительского элемента **EventString** необходимо задать дочерний элемент **File**, **Database** или **Workload** , однако одновременно может использоваться только один из них. Например, если рабочая нагрузка задается элементом **EventString** , то нельзя задавать рабочую нагрузку также элементом **File** в том же входном XML-файле.|  
  
## <a name="element-relationships"></a>Связи элемента  
  
|Связь|Элементы|  
|------------------|--------------|  
|**Родительский элемент**|[Элемент Workload (DTA)](../../tools/dta/workload-element-dta.md)|  
|**Дочерние элементы**|Нет.|  
  
## <a name="example"></a>Пример  
 Пример использования этого элемента см. в разделе [Образец входного XML-файла с описанием встроенной рабочей нагрузки (DTA)](../../tools/dta/xml-input-file-sample-with-inline-workload-dta.md).  
  
## <a name="see-also"></a>См. также:  
 [Справочник по входным XML-файлам (помощник по настройке ядра СУБД)](../../tools/dta/xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
