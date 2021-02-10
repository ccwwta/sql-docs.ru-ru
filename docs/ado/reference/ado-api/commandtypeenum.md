---
description: CommandTypeEnum
title: Коммандтипинум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- CommandTypeEnum
helpviewer_keywords:
- CommandTypeEnum enumeration [ADO]
ms.assetid: 4b1feb9c-a855-40fe-a906-efe688687e9f
author: rothja
ms.author: jroth
ms.openlocfilehash: 01af88e608982499f1acd64c408a93bd0f9c8cca
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100034824"
---
# <a name="commandtypeenum"></a>CommandTypeEnum
Указывает, как должен интерпретироваться аргумент команды.  
  
 Важно проверить предоставленные пользователем значения *CommandString* , чтобы не дать пользователям приложений возможность внедрять потенциально опасные команды для выполнения ADO.  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**адкмдунспеЦифиед**|-1|Не указывает аргумент типа команды.|  
|**adCmdText**|1|Вычисляет [CommandText](./commandtext-property-ado.md) как текстовое определение команды или вызова хранимой процедуры.|  
|**адкмдтабле**|2|Вычисляет **CommandText** как имя таблицы, столбцы которой возвращаются внутренним запросом SQL.|  
|**adCmdStoredProc**|4|Вычисляет **CommandText** в качестве имени хранимой процедуры.|  
|**adCmdUnknown**|8|По умолчанию. Указывает, что тип команды в свойстве **CommandText** неизвестен.<br /><br /> Если тип команды неизвестен, то ADO делает несколько попыток интерпретировать **CommandText**.<br /><br /> -   **CommandText** интерпретируется как текстовое определение команды или вызова хранимой процедуры. Это то же поведение, что и **адкмдтекст**.<br />-   **CommandText** — имя хранимой процедуры. Это то же поведение, что и **адкмдсторедпрок**.<br />-   **CommandText** интерпретируется как имя таблицы. Все столбцы возвращаются внутренним сформированным запросом SQL. Это то же поведение, что и **адкмдтабле**.|  
|**adCmdFile**|256|Вычисляет **CommandText** в качестве имени файла сохраненного [набора записей](./recordset-object-ado.md). Используется с **набором записей.** Только для [открытия или повторного](./open-method-ado-recordset.md) [запроса](./requery-method.md) .|  
|**адкмдтабледирект**|512|Вычисляет **CommandText** как имя таблицы, все столбцы которой возвращаются. Используется с **набором Recordset. Open** или **Requery** only. Чтобы использовать метод [Seek](./seek-method.md) , **набор записей** должен быть открыт с помощью **адкмдтабледирект**.<br /><br /> Это значение не может быть объединено со значением [Ексекутеоптионенум](./executeoptionenum.md) **адасинцексекуте**.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com. MS. WFC. Data**  
  
|Константа|  
|--------------|  
|Адоенумс. CommandType. не указано|  
|Адоенумс. CommandType. TEXT|  
|Адоенумс. CommandType. TABLE|  
|Адоенумс. CommandType. СТОРЕДПРОК|  
|Адоенумс. CommandType. UNKNOWN|  
|Адоенумс. CommandType. FILE|  
|Адоенумс. CommandType. TABLEDIRECT|  
  
## <a name="applies-to"></a>Применение  

:::row:::
    :::column:::
        [Свойство CommandType (ADO)](./commandtype-property-ado.md)  
        [Метод Execute (объект Command ADO)](./execute-method-ado-command.md)  
    :::column-end:::
    :::column:::
        [Метод Execute (объект Connection ADO)](./execute-method-ado-connection.md)  
        [Метод Open (объект Recordset ADO)](./open-method-ado-recordset.md)  
    :::column-end:::
    :::column:::
        [Метод Requery](./requery-method.md)  
    :::column-end:::
:::row-end:::