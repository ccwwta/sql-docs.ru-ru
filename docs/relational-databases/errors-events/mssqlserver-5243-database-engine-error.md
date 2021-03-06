---
description: MSSQLSERVER_5243
title: MSSQLSERVER_5243 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 5243 (Database Engine error)
ms.assetid: e04a1934-e57d-420e-ac79-97071745824e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6cd72c5e595537fd4afa3d33581321b022d55077
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99198105"
---
# <a name="mssqlserver_5243"></a>MSSQLSERVER_5243
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|5243|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя||  
|Текст сообщения|При выполнении внутренней операции была обнаружена несогласованность. Обратитесь в службу технической поддержки. Номер ссылки %ld.|  
  
## <a name="explanation"></a>Объяснение  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] обнаружил несогласованность в структуре подсистемы хранилища, встроенной в память.  
  
## <a name="user-action"></a>Действие пользователя  
Ищите сбой оборудования. Выполните диагностику оборудования и исправьте все найденные проблемы. Просмотрите журнал системы и журнал приложений Windows, а также журнал ошибок SQL Server, чтобы определить, была ли ошибка вызвана сбоем оборудования. Исправьте все обнаруженные в журналах неполадки, связанные с оборудованием.

Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему. Убедитесь, что в системе не включено кэширование записи для контроллера дисков. Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.

В конце концов можно попробовать сменить оборудование. Это может включать форматирование дисков и переустановку операционной системы.

Восстановление из резервной копии. Если проблема не связана с оборудованием и существует заведомо безошибочная резервная копия, восстановите базу данных из этой копии.

Выполнение инструкции DBCC CHECKDB. Если безошибочной резервной копии нет, выполните инструкции DBCC CHECKDB без предложения REPAIR, чтобы определить степень повреждения. Инструкция DBCC CHECKDB выдаст рекомендацию по тому, какое предложение REPAIR следует использовать. После этого выполните инструкцию DBCC CHECKDB с соответствующим предложением REPAIR, чтобы устранить повреждение.

> **тег alert не поддерживается!!!** 
> **тег tr не поддерживается!!!** 
> **тег tr не поддерживается!!!**

Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.
  
## <a name="see-also"></a>См. также:  
[DBCC CHECKDB (Transact-SQL)](~/t-sql/database-console-commands/dbcc-checkdb-transact-sql.md)  
[Файлы и файловые группы базы данных](~/relational-databases/databases/database-files-and-filegroups.md)  
  
