---
description: MSSQLSERVER_17300
title: MSSQLSERVER_17300 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 17300 (Database Engine error)
ms.assetid: c1d6bfb6-28af-4df6-8087-25807602d282
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef6de567f503cd836ee0ef4ed20d9aa601b57250
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99196687"
---
# <a name="mssqlserver_17300"></a>MSSQLSERVER_17300
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |
| :-------- | :---- |
|Название продукта|SQL Server|  
|Идентификатор события|17300|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|PROC_OUT_OF_SYSTASK_SESSIONS|  
|Текст сообщения|SQL Server не удалось запустить новую системную задачу либо из-за недостатка памяти, либо из-за превышения заданного в конфигурации максимального числа сеансов, допустимого для сервера. Проверьте, что на сервере достаточно памяти. Используйте хранимую процедуру sp_configure с параметром «user connections», чтобы выяснить максимально допустимое число соединений пользователя. Текущее число сеансов, включая пользовательские процессы, можно получить из представления sys.dm_exec_sessions.|  
  
## <a name="explanation"></a>Объяснение  
Не удалось запустить новую системную задачу либо из-за недостатка памяти, либо из-за превышения заданного в конфигурации числа сеансов для сервера.  
  
## <a name="user-action"></a>Действие пользователя  
Проверьте, что на сервере достаточно памяти. Проверьте текущее число системных задач с помощью представления sys.dm_exec_sessions и проверьте заданное значение максимального числа соединений пользователя с помощью хранимой процедуры sp_configure.  
  
При необходимости выполните следующие действия.  
  
-   Добавьте память на сервер.  
  
-   Завершите один или несколько сеансов.  
  
-   Увеличьте максимально допустимое число одновременно подключенных пользователей на сервере.  
  
## <a name="see-also"></a>См. также:  
[sp_configure (Transact-SQL)](~/relational-databases/system-stored-procedures/sp-configure-transact-sql.md)  
[Параметры конфигурации сервера (SQL Server)](~/database-engine/configure-windows/server-configuration-options-sql-server.md)  
[sys.dm_exec_sessions (Transact-SQL)](~/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql.md)  
[Настройка параметра конфигурации сервера user connections](~/database-engine/configure-windows/configure-the-user-connections-server-configuration-option.md)  
[KILL (Transact-SQL)](~/t-sql/language-elements/kill-transact-sql.md)  
  
