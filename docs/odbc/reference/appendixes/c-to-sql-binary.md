---
description: 'Преобразование из C в SQL: двоичные данные'
title: 'C в SQL: binary | Документация Майкрософт'
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- binary data type [ODBC]
- data conversions from C to SQL types [ODBC], binary
- binary data transfers [ODBC]
- converting data from c to SQL types [ODBC], binary
ms.assetid: 3e9083f3-357b-41aa-833c-2c8aac2226cd
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: b2e3e1d197a1999c6502848d92222f1c3d6ad5d6
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99212432"
---
# <a name="c-to-sql-binary"></a>Преобразование из C в SQL: двоичные данные
Идентификатор двоичного типа данных ODBC C:  
  
 SQL_C_BINARY  
  
 В следующей таблице показаны типы данных ODBC SQL, к которым могут быть преобразованы двоичные данные C. Описание столбцов и терминов в таблице см. в разделе [Преобразование данных из C в типы данных SQL](../../../odbc/reference/appendixes/converting-data-from-c-to-sql-data-types.md).  
  
|Идентификатор типа SQL|Тест|SQLSTATE|  
|-------------------------|----------|--------------|  
|SQL_CHAR<br /><br /> SQL_VARCHAR<br /><br /> SQL_LONGVARCHAR|Длина байтового <данных = длина столбца в байтах<br /><br /> Длина байта данных > столбца длиной в байтах|н/д<br /><br /> 22001|  
|SQL_WCHAR<br /><br /> SQL_WVARCHAR<br /><br /> SQL_WLONGVARCHAR|Символьная длина <данных = длина символа столбца<br /><br /> Длина символьной длины данных > столбцах|н/д<br /><br /> 22001|  
|SQL_DECIMAL<br /><br /> SQL_NUMERIC<br /><br /> SQL_TINYINT<br /><br /> SQL_SMALLINT<br /><br /> SQL_INTEGER<br /><br /> SQL_BIGINT<br /><br /> SQL_REAL<br /><br /> SQL_FLOAT<br /><br /> SQL_DOUBLE<br /><br /> SQL_BIT SQL_TYPE_DATE<br /><br /> SQL_TYPE_TIME<br /><br /> SQL_TYPE_TIMESTAMP|Длина данных в байтах = длина данных SQL<br /><br /> Длина данных в байтах <> длина данных SQL|н/д<br /><br /> 22003|  
|SQL_BINARY<br /><br /> SQL_VARBINARY<br /><br /> SQL_LONGVARBINARY|Длина <данных = длина столбца<br /><br /> Длина данных > длина столбца|н/д<br /><br /> 22001|
