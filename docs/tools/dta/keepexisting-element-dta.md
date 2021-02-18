---
title: Элемент KeepExisting (DTA)
description: В программе dta элемент KeepExisting указывает структуры физической конструкции, которые помощник по настройке ядра СУБД хранит при создании рекомендаций.
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- KeepExisting element
ms.assetid: e67aae61-d06d-4a03-85ba-6516c3502dce
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.custom: seo-lt-2019
ms.date: 03/01/2017
ms.openlocfilehash: 829500f7335d1cb805b309ef642e6f70393b6912
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100345904"
---
# <a name="keepexisting-element-dta"></a>Элемент KeepExisting (DTA)

 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

Задает структуры физического проектирования (индексы, индексированные представления или секции), по которым помощник по настройке ядра СУБД должен формировать свои рекомендации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <KeepExisting>...</KeepExisting>  
```  
  
## <a name="element-characteristics"></a>Характеристики элемента  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|**Тип данных и длина**|**string**, ограничение длины определяется сервером.|  
|**Допустимые значения**|**NONE**<br /> Существующих структур нет.<br /><br /> **ALL**<br /> Все существующие структуры.<br /><br /> **ALIGNED**<br /> Все структуры, выровненные по секциям.<br /><br /> **CL_IDX**<br /> Все кластеризованные индексы по таблицам.<br /><br /> **IDX**<br /> Все кластеризованные и некластеризованные индексы по таблицам.<br /><br /> С этим элементом следует использовать только одно из данных значений.|  
|**Значение по умолчанию**|Нет.|  
|**Наличие**|Необязательный параметр. Может использоваться только один раз для каждого элемента **TuningOptions** .|  
  
## <a name="element-relationships"></a>Связи элемента  
  
|Связь|Элементы|  
|------------------|--------------|  
|**Родительский элемент**|[Элемент TuningOptions (DTA)](../../tools/dta/tuningoptions-element-dta.md)|  
|**Дочерние элементы**|Нет.|  
  
## <a name="example"></a>Пример  
 Пример использования этого элемента см. в разделе [Образец простого входного файла XML (DTA)](../../tools/dta/simple-xml-input-file-sample-dta.md).  
  
## <a name="see-also"></a>См. также:  
 [Справочник по входным XML-файлам (помощник по настройке ядра СУБД)](../../tools/dta/xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
