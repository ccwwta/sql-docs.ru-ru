---
description: Ограничения параметров хранимой процедуры
title: Ограничения параметров хранимой процедуры | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC], ODBC driver for Oracle
- ODBC driver for Oracle [ODBC], stored procedures
ms.assetid: 8b804bcf-4cce-4e6f-aa45-00bab9ef9921
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: c92ff03bf5cf8899706966169c9b3c770f64f57c
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99188958"
---
# <a name="stored-procedure-parameter-limitations"></a>Ограничения параметров хранимой процедуры
> [!IMPORTANT]  
>  Эта функция будет удалена в следующей версии Windows. Избегайте использования этого компонента в новых разработках и запланируйте изменение существующих приложений, в которых он применяется. Вместо этого используйте драйвер ODBC, предоставляемый Oracle.  
  
 При выполнении хранимых процедур Oracle, использующих 10 или более выходных параметров, вызов хранимой процедуры завершится ошибкой, что приведет к ошибке нарушения прав доступа или объекты данных ActiveX (ADO). Это может произойти при использовании драйвера Microsoft ODBC для Oracle с версиями 8.0.4.0.0 и 8.0.4.0.4 клиентского программного обеспечения Oracle.  
  
 Чтобы устранить эту проблему, необходимо обновить клиентское программное обеспечение Oracle до версии 8.0.4.2.0 или выше. Для получения дополнительных сведений об [исправлениях](../../odbc/microsoft/oracle-software-patches.md)обратитесь к Oracle Corporation.  
  
> [!NOTE]  
>  Эта проблема не возникает в ранних версиях клиентского программного обеспечения Oracle версии 8.0.3.0.0.
