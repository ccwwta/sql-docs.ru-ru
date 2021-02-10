---
description: StringFormatEnum
title: Стрингформатенум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- StringFormatEnum
helpviewer_keywords:
- StringFormatEnum enumeration [ADO]
ms.assetid: 28f7d1ec-092b-4323-a39d-d3f882c6c81a
author: rothja
ms.author: jroth
ms.openlocfilehash: b23a6bc4354f4c67c07bcdc1f4b4d463fff072f2
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100056509"
---
# <a name="stringformatenum"></a>StringFormatEnum
Задает формат при извлечении [набора записей](./recordset-object-ado.md) в виде строки.  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**adClipString**|2|Отделяет строки от *RowDelimiter*, Columns по *ColumnDelimiter* и значения NULL значениями *нуллекспр*. Эти три параметра метода [GetString](./getstring-method-ado.md) допустимы только с *StringFormat* **адклипстринг**.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com. MS. WFC. Data**  
  
|Константа|  
|--------------|  
|Адоенумс. StringFormat. КЛИПСТРИНГ|  
  
## <a name="applies-to"></a>Применение  
 [Метод GetString (ADO)](./getstring-method-ado.md)