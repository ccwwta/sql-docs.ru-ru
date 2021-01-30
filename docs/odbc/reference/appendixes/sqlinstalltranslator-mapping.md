---
description: Сопоставление SQLInstallTranslator
title: Сопоставление SQLInstallTranslator | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- SQLInstallTranslator function [ODBC], mapping
- mapping deprecated functions [ODBC], SQLInstallTranslator
ms.assetid: bcd9ba4f-7834-4bc4-876e-c7478998e524
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: b063768fed57adffd4a6e5051e5383a2ad32a943
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99202706"
---
# <a name="sqlinstalltranslator-mapping"></a>Сопоставление SQLInstallTranslator
Когда приложение ODBC *2. x* вызывает **SQLINSTALLTRANSLATOR** через драйвер ODBC *3. x* , диспетчер драйверов сопоставляет вызов **склинсталлтранслаторекс**. Приложение не должно вызывать **SQLInstallTranslator** в ДИСПЕТЧЕРЕ драйверов ODBC *3. x* с аргументом *лпсзинффиле* , для которого задано значение, отличное от NULL. ODBC. INF-файл, используемый в ODBC *2. x* , больше не поддерживается в ODBC *3. x*, даже для обратной совместимости.
