---
description: Функция SQLInstallTranslator
title: Функция SQLInstallTranslator | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLInstallTranslator
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLInstallTranslator
helpviewer_keywords:
- SQLInstallTranslator function [ODBC]
ms.assetid: 453b21ff-3c2b-4069-8ff7-5c727f062d89
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 40f4c4a5df497c64d081a8d03d1765a4fe5e060a
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99189654"
---
# <a name="sqlinstalltranslator-function"></a>Функция SQLInstallTranslator
**Соответствия**  
 Введенная версия: ODBC 2,5, не рекомендуется  
  
 **Сводка**  
 В ODBC 3,0 **SQLInstallTranslator** был заменен на [склинсталлтранслаторекс](../../../odbc/reference/syntax/sqlinstalltranslatorex-function.md). Вызовы **SQLInstallTranslator** будут сопоставлены с **склинсталлтранслаторекс**. Дополнительные сведения см. в разделе **склинсталлтранслаторекс**.  
  
 **SQLInstallTranslator** возвращает значение false, если приложение вызывает его в ДИСПЕТЧЕРЕ драйверов ODBC *3. x* с аргументом *лпсзинффиле* , для которого задано значение, отличное от NULL. Файл ODBC. INF, используемый в ODBC *2. x* , больше не поддерживается в ODBC *3. x*, даже для обратной совместимости.
