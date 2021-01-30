---
description: Таблицы служб Integration Services (Transact-SQL)
title: Таблицы Integration Services (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- SQL Server Integration Services system tables
- system tables [SQL Server], Integration Services
- system tables [Integration Services]
- SSIS, system tables
ms.assetid: 683b181b-0091-4a9c-86db-bc577af43cec
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c481548f28decfa9fc71a39fc954a52e217feefc
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99205464"
---
# <a name="integration-services-tables-transact-sql"></a>Таблицы служб Integration Services (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  В подразделах этого раздела описываются системные таблицы базы данных msdb, в которых хранятся сведения, используемые [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .  
  
## <a name="in-this-section"></a>в этом разделе  
 [sysssislog](../../relational-databases/system-tables/sysssislog-transact-sql.md)  
 Содержит одну строку для каждой записи журнала, формируемой пакетом служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] во время выполнения.  
  
 Эта таблица используется, только если пакеты используют регистратор [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 [sysssispackagefolders](../../relational-databases/system-tables/sysssispackagefolders-transact-sql.md)  
 Содержит одну строку для каждой логической папки, которую служба [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] использует для организации пакетов. Значения столбцов определяют связь родитель-потомок между вложенными папками.  
  
> [!NOTE]  
>  В среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] хранимые пакеты отображаются в иерархическом представлении после подключения пользователя к службе [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
 [sysssispackages](../../relational-databases/system-tables/sysssispackages-transact-sql.md)  
 Содержит одну строку для каждого пакета служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
 Эта таблица используется, только если пакеты хранятся в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
  
