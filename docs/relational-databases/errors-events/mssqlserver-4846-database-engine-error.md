---
description: MSSQLSERVER_4846
title: MSSQLSERVER_4846 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 4846 (Database Engine error)
ms.assetid: a455e809-1883-4c7d-b3e3-835ee5bfe258
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 789b6220c0b3b61fba1567c88ca5405d7b1e8895
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99185587"
---
# <a name="mssqlserver_4846"></a>MSSQLSERVER_4846
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|4846|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|BULKPROV_MEMORY|  
|Текст сообщения|Поставщику массовых данных не удалось выделить память.|  
  
## <a name="explanation"></a>Объяснение  
Ошибка выделения памяти.  
  
## <a name="user-action"></a>Действие пользователя  
Для диагностики ошибок памяти выполните следующие шаги.  
  
1.  Проверьте, не используют ли память данного сервера другие приложения или службы. Измените настройки таким образом, чтобы менее важные приложения или службы использовали меньший объем памяти.  
  
2.  Начните сбор счетчиков системного монитора для **диспетчера буферов SQL Server, Buffer Manager**, **SQL Server: Memory Manager**.  
  
3.  Проверьте следующие параметры конфигурации памяти SQL Server.  
  
    -   **max server memory**  
  
    -   **min server memory**  
  
    -   **min memory per query**  
  
    Обращайте внимание на любые необычные настройки. При необходимости измените их. Учтите требования [!INCLUDE[ssnoversion](../../includes/ssnoversion-md.md)] к объему памяти. Параметры по умолчанию приведены в разделе «Настройка параметров конфигурации сервера» электронной документации по SQL Server.  
  
4.  Обратите внимание на сообщения инструкции DBCC MEMORYSTATUS и способ их изменения при появлении сообщений об ошибках.  
  
5.  Проверьте рабочую нагрузку (например, число параллельных сеансов, в текущий момент выполняющих запросы).  
  
Следующие действия могут позволить использовать больший объем памяти в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:  
  
-   Если какие-либо отличные от SQL Server приложения используют необходимые ресурсы, попытайтесь прекратить выполнение этих приложений или перенесите их выполнение на отдельный сервер. Это снизит внешнюю нагрузку на память.  
  
-   Если установлен параметр **max server memory**, увеличьте его значение.  
  
Выполните следующие команды DBCC для освобождения нескольких кэшей памяти [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
-   DBCC FREESYSTEMCACHE  
  
-   DBCC FREESESSIONCACHE  
  
-   DBCC FREEPROCCACHE  
  
Если проблема не исчезла, необходимо продолжить ее исследование и, возможно, снизить рабочую нагрузку.  
  
