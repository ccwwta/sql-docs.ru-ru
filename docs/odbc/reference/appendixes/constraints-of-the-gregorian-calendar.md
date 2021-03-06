---
description: Ограничения григорианского календаря
title: Ограничения григорианского календаря | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- data types [ODBC], Gregorian calendar
- Gregorian calendar [ODBC]
ms.assetid: 70667410-c582-4369-8e06-9d98e21cd2bf
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: dbab6e1ef26843807c67e3d3daba9a66e054d8f1
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99165407"
---
# <a name="constraints-of-the-gregorian-calendar"></a>Ограничения григорианского календаря
Типы данных Date и DateTime, а также конечные поля типов данных интервала должны соответствовать ограничениям григорианского календаря. Ниже приведены эти ограничения.  
  
-   Значение поля "месяц" должно быть в диапазоне от 1 до 12 включительно.  
  
-   Значение поля Day должно быть в диапазоне от 1 до количества дней в месяце. Число дней в месяце определяется значениями полей «год» и «месяцы» и может быть 28, 29, 30 или 31. (Количество дней в месяце может также зависеть от того, является ли это високосным годом.)  
  
-   Значение поля Hour должно находиться в диапазоне от 0 до 23 включительно.  
  
-   Значение поля "минута" должно находиться в диапазоне от 0 до 59 включительно.  
  
-   Для поля "конечные секунды" для типов данных интервала значение поля секунд должно находиться в диапазоне от 0 до 59,9 (*n*) включительно, где *n* — число цифр в точности в долях секунды.  
  
-   Для поля "конечные секунды" типов данных DateTime значение поля секунд должно находиться в диапазоне от 0 до 61,9 (*n*) включительно, где *n* указывает количество цифр "9", а значение *n* — точность в долях секунды. (Диапазон секунд позволяет поддерживать синхронизацию сидереал времени в два високосных секунды.)
