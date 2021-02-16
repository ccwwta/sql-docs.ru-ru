---
description: MSSQLSERVER_5009
title: MSSQLSERVER_5009
ms.custom: ''
ms.date: 08/20/2020
ms.prod: sql
ms.reviewer: ramakoni1, pijocoder, suresh-kandoth, Masha
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 5009 (Database Engine error)
ms.assetid: ''
author: suresh-kandoth
ms.author: ramakoni
ms.openlocfilehash: 37a21597feb9372419915151147949539d321116
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100348760"
---
# <a name="mssqlserver_5009"></a>MSSQLSERVER_5009
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

## <a name="details"></a>Сведения

|attribute|Значение|
|---|---|
|Название продукта|SQL Server|
|Идентификатор события|5009|
|Источник события|MSSQLSERVER|
|Компонент|SQLEngine|
|Символическое имя|ALT_BADDISKS|
|Текст сообщения|Не удалось найти или инициализировать один или несколько файлов, перечисленных в инструкции.|
||

## <a name="explanation"></a>Пояснение

Эта ошибка указывает на то, что в команде ALTER DATABASE или DBCC SHRINK* указано имя или идентификатор файла, которые не удалось разрешить.

Рассмотрим следующий сценарий.

- Имеется база данных Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], для которой используется модель полного восстановления или восстановления с неполным протоколированием.
- В нее добавляется новый файл данных с именем *db_file1*.
- Файл `db_file1` задается как файл данных.
- Затем вы понимаете, что тип файла указан неправильно.
- Вы удаляете файл `db_file1`, а затем создаете резервную копию журнала транзакций для базы данных.
- В эту же базу данных добавляется новый файл журнала с именем *db_file1*.
- Вы пытаетесь удалить файл журнала с именем *db_file1* с помощью инструкции ALTER DATABASE или [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Studio.

В этой ситуации вы получаете сообщение об ошибке, которое имеет следующий вид:

> Сообщение 5009, уровень 16, состояние 9, строка 1. Не удалось найти или инициализировать один или несколько файлов, перечисленных в инструкции.

## <a name="possible-causes"></a>Возможные причины

Эта проблема возникает, если логическое имя файла, который вы пытаетесь удалить, не уникально в таблицах системного каталога. Например, она возникает, если файл существовал ранее в базе данных, а затем был удален.

При попытке удалить файл с тем же логическим именем [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] пытается удалить уже удаленный логический файл. Это приводит к сообщению об ошибке.

## <a name="user-action"></a>Рекомендуемые действия

Чтобы обойти эту проблему, выполните следующие действия.

> [!NOTE]
> Они позволяют повторно использовать идентификаторы файлов.

1. С помощью инструкции ALTER DATABASE создайте логический файл с другим именем и тем же типом данных. Например, присвойте логическому файлу имя `different_remove_file_name` вместо `db_file1`, как в следующем примере:

    ```sql
    ALTER DATABASE [DBNAME] ADD FILE ( NAME = N'different_remove_file_name',
    FILENAME = N'D:\MSSQL.1\MSSQL\DATA\db_file1.ndf', SIZE = 1MB, MAXSIZE = 1MB)
    ```

    > [!NOTE]
    > Можно использовать любое имя файла или путь к файлу.

1. С помощью инструкции ALTER DATABASE удалите логический файл, созданный в шаге 1, как в следующем примере:

    ```sql
    ALTER DATABASE [DBNAME] REMOVE FILE [different_remove_file_name]
    ```

1. Создайте резервную копию журнала транзакций базы данных.
1. Попробуйте снова удалить логический файл с именем *db_file1*.
