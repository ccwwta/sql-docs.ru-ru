---
description: MSSQLSERVER_3989
title: MSSQLSERVER_3989
ms.custom: ''
ms.date: 12/25/2020
ms.prod: sql
ms.reviewer: ramakoni1, pijocoder, suresh-kandoth, vencher, tejasaks, docast
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 3989 (Database Engine error)
ms.assetid: ''
author: suresh-kandoth
ms.author: ramakoni
ms.openlocfilehash: 4a32fcdf83c772b881deba596f9884aa74f1effa
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100348786"
---
# <a name="mssqlserver_3989"></a>MSSQLSERVER_3989
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

## <a name="details"></a>Сведения

|attribute|Значение|
|---|---|
|Название продукта|SQL Server|
|Идентификатор события|3989|
|Источник события|MSSQLSERVER|
|Компонент|SQLEngine|
|Символическое имя|XACT_UNSUPPORT_PARALLEL_TRAN3|
|Текст сообщения|Не допускается запуск нового запроса, так как запрос должен содержать допустимый дескриптор транзакции.|
||

## <a name="explanation"></a>Пояснение

Эта ошибка возникает при выполнении распределенного запроса, который соединяет несколько таблиц, размещенных на удаленных экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], и если параметр сеанса `XACT_ABORT` имеет значение **ON**. Пользователю выводится сообщение об ошибке наподобие следующего:

> Сообщение 3989, уровень 16, состояние 1, строка  
Не допускается запуск нового запроса, так как запрос должен содержать допустимый дескриптор транзакции.

## <a name="cause"></a>Причина

При следующих условиях проявляются некоторые ограничения того, как [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] обрабатывает распределенные запросы:

- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] соединяет несколько таблиц одного удаленного источника данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].
- Сеанс, выдающий запрос, не указан в распределенной транзакции.

В этом случае попытка выполнить запрос может вызвать одну из двух ошибок, упомянутых в разделе **Пояснения**.

## <a name="user-action"></a>Рекомендуемые действия

Чтобы устранить эту ошибку, заключите распределенный запрос в инструкцию начала распределенной транзакции:

```sql
BEGIN DISTRIBUTED TRANSACTION <Distributed Query> COMMIT TRANSACTION
```
