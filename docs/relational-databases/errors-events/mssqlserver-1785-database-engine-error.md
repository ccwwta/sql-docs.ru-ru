---
description: MSSQLSERVER_1785
title: MSSQLSERVER_1785
ms.custom: ''
ms.date: 12/25/2020
ms.prod: sql
ms.reviewer: ramakoni1, pijocoder, suresh-kandoth, vencher, tejasaks, docast
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 1785 (Database Engine error)
ms.assetid: ''
author: suresh-kandoth
ms.author: ramakoni
ms.openlocfilehash: 6adb44b26ca0af5ab00476c680c924875cd50d2d
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100348825"
---
# <a name="mssqlserver_1785"></a>MSSQLSERVER_1785
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

## <a name="details"></a>Сведения

|attribute|Значение|
|---|---|
|Название продукта|SQL Server|
|Идентификатор события|1785|
|Источник события|MSSQLSERVER|
|Компонент|SQLEngine|
|Символическое имя|CRTFKINVTOPO|
|Текст сообщения|Введение ограничения FOREIGN KEY "%.ls" для таблицы "%. ls" может привести к появлению циклов или множественных каскадных путей. Укажите ON DELETE NO ACTION или ON UPDATE NO ACTION либо измените другие ограничения внешнего ключа (FOREIGN KEY).|
||

## <a name="explanation"></a>Пояснение

Это сообщение об ошибке появляется из-за того, что в SQL Server таблица не может появляться более одного раза в списке всех каскадных ссылочных действий, запускаемых инструкцией `DELETE` или `UPDATE`. Дерево каскадных ссылочных действий должно иметь только один путь к определенной таблице в дереве каскадных ссылочных действий.

Пользователю выводится сообщение об ошибке наподобие следующего:

> Сервер:  Сообщение 1785, уровень 16, состояние 1, строка 1. Введение ограничения FOREIGN KEY "fk_two" для таблицы "table2" может привести к появлению циклов или множественных каскадных путей. Укажите ON DELETE NO ACTION или ON UPDATE NO ACTION либо измените другие ограничения внешнего ключа (FOREIGN KEY). Сервер:  Сообщение 1750, уровень 16, состояние 1, строка 1. Не удалось создать ограничение. См. описание предыдущих ошибок.

## <a name="user-action"></a>Рекомендуемые действия

Чтобы устранить эту проблему, создайте внешний ключ, который создаст один путь к таблице в списке каскадных ссылочных действий.

Обеспечить целостность ссылок можно несколькими способами. Декларативная ссылочная целостность (DRI) — это самый простой, но и наименее гибкий способ. Если требуется большая гибкость с сохранением высокого уровня целостности, можно использовать триггеры.

## <a name="more-information"></a>Дополнительные сведения

Следующий пример кода демонстрирует попытку создания внешнего ключа, которая приводит к сообщению об ошибке:

```sql
USE tempdb
GO

CREATE TABLE table1 (user_ID INTEGER NOT NULL PRIMARY KEY, user_name
CHAR(50) NOT NULL)
GO

CREATE TABLE table2 (author_ID INTEGER NOT NULL PRIMARY KEY, author_name
CHAR(50) NOT NULL, lastModifiedBy INTEGER NOT NULL, addedby INTEGER NOT NULL)
GO

ALTER TABLE table2 ADD CONSTRAINT fk_one FOREIGN KEY (lastModifiedby)
REFERENCES table1 (user_ID) ON DELETE CASCADE ON UPDATE cascade
GO

ALTER TABLE table2 ADD CONSTRAINT fk_two FOREIGN KEY (addedby)
REFERENCES table1(user_ID) ON DELETE NO ACTION ON UPDATE cascade
GO
--this fails with the error because it provides a second cascading path to table2.

ALTER TABLE table2 ADD CONSTRAINT fk_two FOREIGN KEY (addedby)
REFERENCES table1 (user_ID) ON DELETE NO ACTION ON UPDATE NO ACTION
GO
-- this works.
```

### <a name="see-also"></a>См. также раздел

[Каскадная ссылочная целостность](../tables/primary-and-foreign-key-constraints.md#referential-integrity)