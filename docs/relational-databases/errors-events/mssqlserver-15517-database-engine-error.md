---
description: MSSQLSERVER_15517
title: MSSQLSERVER_15517 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 15517 (Database Engine error)
ms.assetid: f94287f5-129f-4c52-9d34-62b996088001
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 592439f0e90f1b8ba607f518ad5125510b8e8a3e
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99196896"
---
# <a name="mssqlserver_15517"></a>MSSQLSERVER_15517
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|Идентификатор события|15517|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|SEC_CANNOTEXECUTEASUSER|  
|Текст сообщения|Невозможно выполнить в качестве участника базы данных, поскольку участник "*участник*" не существует, этот тип участника не может проходить олицетворение или отсутствует разрешение.|  
  
## <a name="user-action"></a>Действие пользователя  
Используйте имя существующего участника или получите разрешение IMPERSONATE для этого участника.  
  
15517 может также возникнуть после присоединения и восстановления базы данных пользователем, который не является ее изначальным владельцем. Чтобы устранить эту ошибку, измените db_owner на имя входа на сервере с помощью следующей команды:  
  
```  
ALTER AUTHORIZATION ON DATABASE:: DBName TO [NewLogin]  
```  
  
## <a name="see-also"></a>См. также:  
[Выполняющаяся в памяти OLTP (оптимизация в памяти)](~/relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
