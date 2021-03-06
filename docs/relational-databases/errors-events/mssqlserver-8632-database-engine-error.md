---
description: MSSQLSERVER_8632
title: MSSQLSERVER_8632
ms.custom: ''
ms.date: 10/27/2020
ms.prod: sql
ms.reviewer: ramakoni1, pijocoder, suresh-kandoth, vencher, tejasaks, docast
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 8632 (Database Engine error)
ms.assetid: ''
author: suresh-kandoth
ms.author: ramakoni
ms.openlocfilehash: b7c59634423bd6df623725720bf8bd0d262d5be0
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100348693"
---
# <a name="mssqlserver_8632"></a>MSSQLSERVER_8632
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

## <a name="details"></a>Сведения

|attribute|Значение|
|---|---|
|Название продукта|SQL Server|
|Идентификатор события|8632|
|Источник события|MSSQLSERVER|
|Компонент|SQLEngine|
|Символическое имя|QUERY_EXPRESSION_TOO_COMPLEX|
|Текст сообщения|Внутренняя ошибка: был достигнут предел служб выражений. Проверьте потенциально сложные выражения в запросе и постарайтесь их упростить.|
||

## <a name="explanation"></a>Объяснение

Ошибка 8632 возникает при выполнении запроса в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], который содержит большое количество идентификаторов и констант в одном выражении. Пользователю выводится сообщение об ошибке наподобие следующего:

> Сервер:  Сообщение 8632, уровень 17, состояние 2, строка 1  
Внутренняя ошибка: был достигнут предел служб выражений. Проверьте потенциально сложные выражения в запросе и постарайтесь их упростить.

## <a name="cause"></a>Причина

Эта ошибка возникает, потому что в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] есть ограничение на количество идентификаторов и констант, которые могут содержаться в одном выражении запроса. Превышение этого количества приводит к ошибке SQL Server (ошибка 8632). Например, следующий запрос содержит только одно выражение:

```sql
select a, b + c, d + e
```

Это выражение извлекает все пять столбцов, вычисляет операторы сложения и отправляет клиенту три спроецированных результата.

Проверка числа идентификаторов и констант выполняется после того, как [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] развертывает все упоминаемые идентификаторы и константы. Например, могут развертываться следующие элементы:

- звездочка (*) в списке выбора;
- представление;
- определение вычисляемого столбца.

Если число идентификаторов и констант после развертывания превышает ограничение, выполнить запрос невозможно.

## <a name="user-action"></a>Рекомендуемые действия

Для обхода этой проблемы измените запрос. Используйте меньше идентификаторов и констант в самом большом выражении в запросе. Количество идентификаторов и констант в каждом выражении запроса не должно превышать ограничение. Для этого может потребоваться разбить запрос на несколько отдельных с временными промежуточными результатами.
