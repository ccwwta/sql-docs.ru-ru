---
description: Ограничения зарезервированных ключевых слов
title: Ограничения зарезервированных слов | Документация Майкрософт
ms.custom: ''
ms.date: 05/01/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- ODBC desktop database drivers [ODBC]
- desktop database drivers [ODBC]
ms.assetid: ed42f083-c9e8-4ee4-9d64-d879bf955c78
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: e615ab4c8222ec7ac679f96f360458dfaab5abb9
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99182568"
---
# <a name="reserved-keyword-limitations"></a>Ограничения зарезервированных ключевых слов

Не используйте зарезервированные ключевые слова ODBC в качестве идентификаторов в таблицах SQL или связанных объектах. Если возникает случай, когда в качестве идентификатора необходимо использовать зарезервированное ключевое слово, необходимо заключить идентификатор в пару обратных *импульсов* ('). Другое *имя для* *обратной стороны — Обратная кавычка*.

Зарезервированное ограничение ключевого слова также применяется к любой сокращенной форме зарезервированных ключевых слов.

Список зарезервированных ключевых слов ODBC можно найти по адресу:

- [Зарезервированные ключевые слова ODBC](../reference/appendixes/reserved-keywords.md).

- В *справочном руководстве программиста по ODBC* см. [Приложение C: грамматика SQL](../reference/appendixes/appendix-c-sql-grammar.md).