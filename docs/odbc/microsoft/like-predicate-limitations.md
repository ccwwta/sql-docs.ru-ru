---
description: Ограничения предиката LIKE
title: Ограничения предиката LIKE | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- LIKE predicate limitations [ODBC]
- ODBC SQL grammar, LIKE predicate limitations
ms.assetid: dbd39099-caf6-4c4c-9ad8-f6c63c1bd5e4
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 4925ff83d8dafc1cce7c0a58a17685fcf30371f6
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99199897"
---
# <a name="like-predicate-limitations"></a>Ограничения предиката LIKE
Если длина данных в столбце превышает 255 символов, сравнение LIKE будет основано только на первых 255 символах.  
  
 , Как используется в процедуре, поддерживается только с шаблонами констант. Драйверы базы данных для настольных систем поддерживают SQL-92, например сопоставление шаблонов.  
  
 Использование предложения ESCAPE в предикате LIKE не поддерживается.  
  
 Сравнение со значением LIKE не должно выполняться для столбца, содержащего данные типа данных numeric или float. Результаты могут быть непредсказуемыми. Дополнительные сведения см. в *статье Microsoft Jet ядро СУБД программиста*.
