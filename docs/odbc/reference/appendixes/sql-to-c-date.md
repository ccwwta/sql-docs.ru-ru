---
description: 'Преобразование данных из SQL в C: даты'
title: 'SQL в C: Дата | Документация Майкрософт'
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- converting data from SQL to C types [ODBC], date
- date data type [ODBC]
- data conversions from SQL to C types [ODBC], date
ms.assetid: 703c7960-9cf4-4d7a-9920-53b29c184f97
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 9909d0344c2df53212be54e4c695b121c0717e78
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99203044"
---
# <a name="sql-to-c-date"></a>Преобразование данных из SQL в C: даты
Идентификатор для типа данных ODBC SQL:  
  
 SQL_TYPE_DATE  
  
 В следующей таблице показаны типы данных ODBC C, к которым могут быть преобразованы данные SQL. Описание столбцов и терминов в таблице см. в разделе [Преобразование данных из SQL в типы данных C](../../../odbc/reference/appendixes/converting-data-from-sql-to-c-data-types.md).  
  
|Идентификатор типа C|Тест|**таржетвалуептр*|**StrLen_or_IndPtr*|SQLSTATE|  
|-----------------------|----------|------------------------|----------------------------|--------------|  
|SQL_C_CHAR|*BufferLength* длина байта > символов<br /><br /> 11 <= *BufferLength* <= Длина байтового символа<br /><br /> *BufferLength* < 11|Данные<br /><br /> Усеченные данные<br /><br /> Не определено.|10<br /><br /> Длина данных в байтах<br /><br /> Не определено.|н/д<br /><br /> 01004<br /><br /> 22003|  
|SQL_C_WCHAR|Длина *BufferLength* > символов<br /><br /> 11 <= *BufferLength* <= длина символа<br /><br /> *BufferLength* < 11|Данные<br /><br /> Усеченные данные<br /><br /> Не определено.|10<br /><br /> Длина данных в символах<br /><br /> Не определено.|н/д<br /><br /> 01004<br /><br /> 22003|  
|SQL_C_BINARY|Длина данных в байтах <= *BufferLength*<br /><br /> Длина байта данных > *BufferLength*|Данные<br /><br /> Не определено.|Длина данных в байтах<br /><br /> Не определено.|н/д<br /><br /> 22003|  
|SQL_C_TYPE_DATE|Нет [a]|Данные|6 [c]|н/д|  
|SQL_C_TYPE_TIMESTAMP|Нет [a]|Данные [b]|16 [c]|н/д|  
  
 [a] значение *BufferLength* игнорируется для этого преобразования. Драйвер предполагает, что размер **таржетвалуептр* — это размер типа данных C.  
  
 [b] поля времени структуры метки времени имеют нулевое значение.  
  
 [c] это размер соответствующего типа данных C.  
  
 Когда дата SQL преобразуется в символьные данные C, результирующая строка находится в формате "*гггг* - *мм* - *дд*". На этот формат не влияет параметр Windows® Country.
