---
description: Поддержка типов данных
title: Поддержка типов данных | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- minimum SQL syntax supported [ODBC]
- ODBC drivers [ODBC], minimum SQL syntax supported
- data types [ODBC], ODBC drivers
- ODBC drivers [ODBC], data types
ms.assetid: 782b4490-372b-4366-aad7-a486fb8a07c8
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 5b9249539c87e727b293c73ee12ed0fa734e08fa
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99179539"
---
# <a name="data-type-support"></a>Поддержка типов данных
Драйверы ODBC должны поддерживать хотя бы один SQL_CHAR и SQL_VARCHAR. Поддержка других типов данных определяется уровнем соответствия SQL-92 источника данных или драйвера. Приложение должно вызывать **SQLGetTypeInfo** для определения типов данных, поддерживаемых драйвером.  
  
 Дополнительные сведения о типах данных см. в разделе [Приложение D. типы данных](../../../odbc/reference/appendixes/appendix-d-data-types.md).
