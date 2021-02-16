---
description: MSSQLSERVER_
title: MSSQLSERVER_4214
ms.custom: ''
ms.date: 08/20/2020
ms.prod: sql
ms.reviewer: ramakoni1, pijocoder, suresh-kandoth, Masha
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 4214 (Database Engine error)
ms.assetid: ''
author: suresh-kandoth
ms.author: ramakoni
ms.openlocfilehash: 1ccce1ca406527cfca2485bec41f2fb9d287862c
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100348776"
---
# <a name="mssqlserver_4214"></a>MSSQLSERVER_4214
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

## <a name="details"></a>Сведения

|attribute|Значение|
|---|---|
|Название продукта|SQL Server|
|Идентификатор события|4214|
|Источник события|MSSQLSERVER|
|Компонент|SQLEngine|
|Символическое имя|DMPX_NODBBACKUP|
|Текст сообщения|Инструкцию BACKUP LOG невозможно выполнить, так как не существует резервной копии текущей базы данных.|
||

## <a name="explanation"></a>Пояснение

Эта ошибка возникает при попытке выполнить резервное копирование журнала транзакций перед полным резервным копированием базы данных. Перед тем как выполнять резервное копирование журнала транзакций для базы данных, необходимо произвести ее полное резервное копирование. Кроме того, в журнале ошибок появится следующее сообщение:

> Резервное копирование \<Datetime>    Ошибка: 3041, серьезность: 16, состояние: 1.  
Резервное копирование \<Datetime>     BACKUP не выполнила команду BACKUP LOG \<db_name>. Проверьте дополнительные сообщения в журнале приложения резервного копирования.

## <a name="user-action"></a>Рекомендуемые действия

Перед тем как выполнять резервное копирование журнала транзакций для базы данных, произведите ее полное резервное копирование.

## <a name="more-information"></a>Дополнительные сведения

Дополнительные сведения см. в следующей статье: [Резервное копирование и восстановление баз данных SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md).