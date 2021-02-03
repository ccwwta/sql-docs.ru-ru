---
description: MSSQLSERVER_10520
title: MSSQLSERVER_10520 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 10520 (Database Engine error)
ms.assetid: cc8799f1-5b90-4248-b209-e1d5087f9529
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0f2187ccd80b90c0375ae960bd4e27806640e74b
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99197446"
---
# <a name="mssqlserver_10520"></a>MSSQLSERVER_10520
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|10520|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|PG_PARAM_NOT_ALLOWED|  
|Текст сообщения|Не удается создать структуру плана '%.*ls', поскольку для параметра @type указано значение '%!s', а для параметра '%!s' указано значение, отличное от NULL. Для заданного типа этот параметр должен иметь значение NULL. Укажите для этого параметра значение NULL либо измените его тип таким образом, чтобы он допускал значение, отличное от NULL.|  
  
## <a name="explanation"></a>Объяснение  
Для типа, указанного в @type, требуется значение NULL, но предоставлено значение, отличное от NULL.  
  
## <a name="user-action"></a>Действие пользователя  
Укажите для этого параметра значение NULL либо измените его тип таким образом, чтобы он допускал значение, отличное от NULL.  
  
## <a name="see-also"></a>См. также:  
[sp_create_plan_guide (Transact-SQL)](~/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql.md)  
[Руководства планов](~/relational-databases/performance/plan-guides.md)  
  
