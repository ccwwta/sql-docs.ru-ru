---
description: Вызов SQLSetPos для вставки данных
title: Вызов функции SQLSetPos для вставки данных | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- compatibility [ODBC], SQLSetPos
- SQLSetPos function [ODBC], inserting data
- backward compatibility [ODBC], SqlSetPos
ms.assetid: 03e5c4d0-2bb3-4649-9781-89cab73f78eb
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 6c9ddd58e9f463d7878bb4b9b8710ce0e6dfecc4
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99110901"
---
# <a name="calling-sqlsetpos-to-insert-data"></a>Вызов SQLSetPos для вставки данных
Когда приложение ODBC *2. x* , работающее с драйвером ODBC *3. x* , вызывает функцию **SQLSetPos** с аргументом *операции* SQL_ADD, диспетчер драйверов не сопоставляет этот вызов с **SQLBulkOperations**. Если драйвер ODBC *3. x* должен работать с приложением, которое вызывает функцию **SQLSetPos** с SQL_ADD, драйвер должен поддерживать эту операцию.  
  
 Одно из основных различий в поведении при вызове функции **SQLSetPos** с SQL_ADD возникает при вызове в состоянии S6. В ODBC *2. x* Драйвер возвратил S1010, когда функция **SQLSetPos** была вызвана с SQL_ADD в состоянии S6 (после того, как курсор был помещен в **SQLFetch**). В ODBC *3. x* **SQLBulkOperations** с *операцией* SQL_ADD можно вызвать в состоянии S6. Второе основное различие в поведении заключается в том, что **SQLBulkOperations** с *операцией* SQL_ADD можно вызвать в состоянии S5, а **SQLSetPos** с **операцией** SQL_ADD не может. Для переходов инструкций, которые могут возникать для одного и того же вызова в ODBC *3. x*, см. [приложение б. таблицы переходов состояния ODBC](../../../odbc/reference/appendixes/appendix-b-odbc-state-transition-tables.md).
