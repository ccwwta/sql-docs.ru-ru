---
description: MSSQLSERVER_8443
title: MSSQLSERVER_8443 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 8443 (Database Engine error)
ms.assetid: a3541b9c-b1a8-4280-add1-275f08696b62
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f254afa4a60e1f2ef21efd70ee75271ebd759548
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99186780"
---
# <a name="mssqlserver_8443"></a>MSSQLSERVER_8443
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|8443|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|SB_DIALOG_WO_CONV_GROUP|  
|Текст сообщения|Диалог с идентификатором "%.*ls" и инициатором %d указывает на несуществующую группу сообщений "%.\*ls". Запустите DBCC CHECKDB для анализа и восстановления базы данных.|  
  
## <a name="explanation"></a>Объяснение  
Для группы сообщений слой метаданных возвратил значение NULL. База данных каким-то образом повреждена. Одним из возможных источников повреждений является ошибка жесткого диска.  
  
## <a name="user-action"></a>Действие пользователя  
Запустите DBCC CHECKDB в режиме исправлений для восстановления базы данных до согласованного состояния. При восстановлении согласованности возможно удаление сообщений. Изучите журналы ошибок системы, чтобы понять, не возникла ли эта ошибка в результате другой неисправности в системе.  
  
