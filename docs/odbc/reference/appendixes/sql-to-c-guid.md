---
description: 'Преобразование данных из SQL в C: GUID'
title: 'С SQL на C: GUID | Документация Майкрософт'
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- converting data from SQL to C types [ODBC], GUID
- data conversions from SQL to C types [ODBC], guid
- GUID data type [ODBC]
ms.assetid: cf56c684-c261-4b89-994a-db14ab2241d6
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 9b55b88414dfa78b80c49987af6dab82ba4abeda
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99203032"
---
# <a name="sql-to-c-guid"></a>Преобразование данных из SQL в C: GUID
Идентификатором для типа данных ODBC SQL является:  
  
 SQL_GUID  
  
 В следующей таблице показаны типы данных ODBC C, к которым могут быть преобразованы данные SQL в GUID. Описание столбцов и терминов в таблице см. в разделе [Преобразование данных из SQL в типы данных C](../../../odbc/reference/appendixes/converting-data-from-sql-to-c-data-types.md).  
  
|Идентификатор типа C|Тест|**таржетвалуептр*|**StrLen_or_IndPtr*|SQLSTATE|  
|-----------------------|----------|------------------------|----------------------------|--------------|  
|SQL_C_CHAR|*BufferLength* длина байта > символов|Данные|36|н/д|  
||*BufferLength* < 37|Не определено|Не определено|22003|  
|SQL_C_WCHAR|Длина *BufferLength* > символов|Данные|36|н/д|  
||*BufferLength* < 37|Не определено|Не определено|22003|  
|SQL_C_BINARY|Длина BufferLength данных в байтах \< =  |Данные|Длина данных в байтах|н/д|  
||Длина байта данных > *BufferLength*|Не определено|Не определено|22003|  
|SQL_C_GUID|Нет [a]|Данные|16 [b]|н/д|  
  
 [a] значение *BufferLength* игнорируется для этого преобразования. Драйвер предполагает, что размер **таржетвалуептр* — это размер типа данных C.  
  
 [b] это размер соответствующего типа данных C.
