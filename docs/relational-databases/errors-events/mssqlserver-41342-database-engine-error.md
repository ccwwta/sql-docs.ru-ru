---
description: MSSQLSERVER_41342
title: MSSQLSERVER_41342 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 41342 (Database Engine error)
ms.assetid: 28270d98-c543-4e7d-b40c-2200e38dce1c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 638f0758a28a7a2a03a9f9abcbbfb82181948548
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99179564"
---
# <a name="mssqlserver_41342"></a>MSSQLSERVER_41342
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|Идентификатор события|41342|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|HK_HW_NOT_SUPPORTED|  
|Текст сообщения|Модель процессора в системе не поддерживает создание *конструкция*. Эта ошибка обычно возникает со старыми процессорами.|  
  
## <a name="explanation"></a>Объяснение  
Для оптимизированных для памяти таблиц требуется модель процессора, которая поддерживает операции сравнения и обмена с 128-разрядными значениями, для чего требуется инструкция сборки CMPXCHG16B. Некоторые старые модели процессоров AMD не поддерживают инструкцию CMPXCHG16B. Кроме того, некоторые среды виртуализации не включают эту инструкцию по умолчанию.  
  
## <a name="user-action"></a>Действие пользователя  
Обновите процессор. Если процессор поддерживает инструкцию, а SQL Server выполняется в виртуальной машине, измените конфигурацию, чтобы включить поддержку инструкции CMPXCHG16B.  
  
## <a name="see-also"></a>См. также:  
[Выполняющаяся в памяти OLTP (оптимизация в памяти)](~/relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
