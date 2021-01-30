---
description: Маркеры параметров
title: Маркеры параметров | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- minimum SQL syntax supported [ODBC]
- ODBC drivers [ODBC], minimum SQL syntax supported
- parameter markers [ODBC]
ms.assetid: 07213d04-cd31-45fd-a8c8-2e16e09eeaf4
author: David-Engel
ms.author: v-daenge
ms.reviewer: ''
ms.openlocfilehash: 7ab9b0cd8682ecc722f97b563285bdd31665c1fd
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99205334"
---
# <a name="parameter-markers"></a>Маркеры параметров
В соответствии со спецификацией SQL-92 приложение не может размещать маркеры параметров в следующих местах. Более полный список см. в спецификации SQL-92.  
  
-   В списке **выбора**  
  
-   Как оба *выражения* в *предикате сравнения*  
  
-   Как оба операнда бинарного оператора  
  
-   В качестве первого и второго операнда **между** операциями  
  
-   Как первый и третий операнды **между** операциями  
  
-   Как выражение и первое значение **в** операции  
  
-   Как операнд унарной операции + или-  
  
-   В качестве аргумента для *ссылки Set-Function*  
  
 Дополнительные сведения о маркерах параметров см. в спецификации SQL-92. Дополнительные сведения о параметрах см. в разделе [Параметры инструкции](../../../odbc/reference/develop-app/statement-parameters.md).
