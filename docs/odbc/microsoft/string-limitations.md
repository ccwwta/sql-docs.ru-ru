---
description: Ограничения строк
title: Ограничения строк | Документация Майкрософт
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
ms.assetid: ec1da65f-c69d-415d-bf75-8fda8aa2b39f
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 12d02a6e69b34c13219e4bb5f00aeacfa9945cfb
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99188932"
---
# <a name="string-limitations"></a>Ограничения строк
Максимальная длина строки инструкции SQL — 65 000 символов.  
  
 При использовании драйвера Microsoft Access поддерживаются только строковые константы SQL-92 (с одиночными кавычками, а не двойные кавычки).  
  
 Символ вертикальной черты (&#124;) нельзя использовать в строке, независимо от того, заключен символ в обратные кавычки или нет.  
  
 Для обеспечения максимальной совместимости приложения должны передавать строки в параметрах вместо передачи строк в кавычках.
