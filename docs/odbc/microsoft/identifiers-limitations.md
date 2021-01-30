---
description: Ограничения идентификаторов
title: Ограничения идентификаторов | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- ODBC desktop database drivers [ODBC]
- desktop database drivers [ODBC]
ms.assetid: b3466382-71cb-4f82-8318-092a8fcef3df
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 71141e8f695b4ac6e60e6aecd70648f412807abb
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99190926"
---
# <a name="identifiers-limitations"></a>Ограничения идентификаторов
Если идентификатор содержит пробел или специальный символ, идентификатор должен быть заключен в обратные кавычки. Допустимое имя — это строка, в которой не более 64 символов, первый символ не должен быть пробелом. Допустимые имена не могут содержать управляющие символы или следующие специальные символы: "&#124; # *? [ ] . ! $ .  
  
 Не используйте зарезервированные слова, перечисленные в грамматике SQL в приложении C *Справочника программиста ODBC* (или сокращенной формы этих зарезервированных слов) в качестве идентификаторов (т. е. имен таблиц или столбцов), если слова не заключены в обратные кавычки (').
