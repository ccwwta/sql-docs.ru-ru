---
description: MSSQLSERVER_17883
title: MSSQLSERVER_17883 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 17883 (Database Engine error)
ms.assetid: adaf1c04-e397-4a69-90b8-9353a37277ea
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f1d8aa071f3bed7171939cdef0687852c20c9b73
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99196615"
---
# <a name="mssqlserver_17883"></a>MSSQLSERVER_17883
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|17883|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|SRV_SCHEDULER_NONYIELDING|  
|Текст сообщения|Процесс %ld:%ld:%ld (0x%lx) Worker 0x%p, по-видимому, не возвращает управление планировщику %ld. Время создания потока: %I64d. Примерная загрузка ЦП для потока: ядро %I64d мс, пользователь %I64d мс. Эффективность использования процесса %d%%. Бездействие системы %d%%. Интервал: %I64d мс.|  
  
## <a name="explanation"></a>Объяснение  
Указывает на возможную проблему, в результате которой поток не возвращает управление планировщику.  Возможно, это сбой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] либо [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не получает достаточно циклов процессора для выполнения.  Эта ошибка может исчезнуть, если поток, в конце концов, передаст управление.  
  
## <a name="user-action"></a>Действие пользователя  
В случае избыточной нагрузки на систему уменьшите ее. В противном случае обратитесь в службу поддержки пользователей Майкрософт.  
  
