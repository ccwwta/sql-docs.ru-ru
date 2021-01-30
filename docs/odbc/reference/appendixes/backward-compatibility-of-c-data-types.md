---
description: Обратная совместимость типов данных C
title: Обратная совместимость типов данных C | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- backward compatibility [ODBC], C data types
- compatibility [ODBC], C data types
- data types [ODBC], backward compatibility
- C data types [ODBC], backward compatibility
ms.assetid: b1453a65-ae03-4061-b0cf-a8434d8bc40b
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 75ea0c53091faaece23f9d7316c9a6f242677a41
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99212505"
---
# <a name="backward-compatibility-of-c-data-types"></a>Обратная совместимость типов данных C
SQL_C_SHORT, SQL_C_LONG и SQL_C_TINYINT были заменены в ODBC с помощью подписанных и неподписанных типов: SQL_C_SSHORT и SQL_C_USHORT, SQL_C_SLONG и SQL_C_ULONG, а SQL_C_STINYINT и SQL_C_UTINYINT. Драйвер ODBC *3. x* , который должен работать с приложениями ODBC *2. x* , должен поддерживать SQL_C_SHORT, SQL_C_LONG и SQL_C_TINYINT, поскольку при их вызове диспетчер драйверов передает их в драйвер.
