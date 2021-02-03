---
description: MSSQLSERVER_3156
title: MSSQLSERVER_3156 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 3156 (Database Engine error)
ms.assetid: 345d8ed4-177e-4ec3-bab3-25d30000e323
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: efb73d7de68c2efea9eca6d8b918697e24a69172
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99209764"
---
# <a name="mssqlserver_3156"></a>MSSQLSERVER_3156
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|Идентификатор события|3156|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|LDDB_CANT_WRITE|  
|Текст сообщения|Невозможно восстановить файл «%ls» до «%ls». Укажите допустимое расположение для файла с помощью предложения WITH MOVE.|  
  
## <a name="explanation"></a>Объяснение  
Это общее сообщение идентифицирует логические или физические имена файлов, которые не удалось восстановить из-за ошибок в заданном расположении.  
  
### <a name="possible-causes"></a>Возможные причины  
Ниже приведены возможные причины.  
  
-   Возможно, необходим доступ к указанному каталогу Windows.  
  
-   Возможно, введен или указан несуществующий путь.  
  
-   Указано имя файла, который недоступен для перезаписи.  
  
## <a name="user-action"></a>Действие пользователя  
Найдите в журналах ошибок другие сообщения, содержащие дополнительные сведения.  
  
Устраните неполадку, связанную с указанным расположением. Для этого, например, предоставьте необходимые права доступа или измените расположение файла с помощью параметра WITH MOVE предложения RESTORE.  
  
## <a name="see-also"></a>См. также:  
[Восстановление базы данных в новом расположении (SQL Server)](~/relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md)  
[Восстановление файлов в новое место (SQL Server)](~/relational-databases/backup-restore/restore-files-to-a-new-location-sql-server.md)  
[RESTORE (Transact-SQL)](~/t-sql/statements/restore-statements-transact-sql.md)  
  
