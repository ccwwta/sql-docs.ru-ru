---
description: MSSQLSERVER_41399
title: MSSQLSERVER_41399 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 41399 (Database Engine error)
ms.assetid: 5e5acb07-16ca-4329-8210-cd2bab0c904f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1d031d704b3457dca1d8d0926825475a9cdba8a4
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99179341"
---
# <a name="mssqlserver_41399"></a>MSSQLSERVER_41399
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|Идентификатор события|41399|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|MAX_SORT_ROW_WIDTH_EXCEEDED|  
|Текст сообщения|Слишком сложная операция сортировки. Дополнительные сведения см. в электронной документации по SQL Server.|  
  
## <a name="explanation"></a>Объяснение  
Сортировка результата операций соединения и агрегации увеличивает сложность операции сортировки за счет увеличения размера строки в буфере сортировки. Эта ошибка означает, что размер строки превышает максимальный размер, поддерживаемый оператором сортировки в изначально скомпилированных хранимых процедурах. Обратите внимание, что размер строки в буфере сортировки определяется только количеством соединений и количеством и типом агрегатных функций. Размер строк в базовых таблицах не влияет на размер строки в буфере.  
  
## <a name="user-action"></a>Действие пользователя  
Уменьшить сложность запроса путем удаления соединений или агрегатных функций.  
  
## <a name="see-also"></a>См. также:  
[Выполняющаяся в памяти OLTP (оптимизация в памяти)](~/relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
