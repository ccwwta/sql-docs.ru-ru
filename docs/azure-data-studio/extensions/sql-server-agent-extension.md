---
title: Расширение агента SQL Server
description: Узнайте, как установить и использовать расширение агента SQL Server для Azure Data Studio, которое предназначено для управления заданиями и конфигурациями агента SQL Server.
ms.prod: azure-data-studio
ms.technology: azure-data-studio
ms.topic: conceptual
author: yualan
ms.author: alayu
ms.reviewer: maghan, sstein
ms.custom: seodec18
ms.date: 09/24/2018
ms.openlocfilehash: 6bec78ab2c79af6f6a4dca70b25345f567def48b
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100040274"
---
# <a name="sql-server-agent-extension-preview"></a>Расширение агента SQL Server (предварительная версия)

Расширение агента SQL Server (предварительная версия) — это расширение для управления заданиями и конфигурациями агента SQL Server и устранения связанных с ними неполадок. Сейчас это расширение находится в режиме предварительной версии.

Ниже указаны основные действия, выполняемые с помощью расширения.

- Вывод списка заданий агента SQL Server, настроенных в SQL Server
- Просмотр журнала заданий с результатами выполнения заданий
- Базовое управление заданиями для запуска и остановки заданий

## <a name="install-the-sql-server-agent-extension"></a>Установка расширения агента SQL Server

1. Чтобы открыть диспетчер расширений и получить доступ к имеющимся расширениям, щелкните значок расширений или выберите пункт **Расширения** в меню **Вид**.
2. Выберите доступное расширение и просмотрите сведения о нем.

   ![Установка агента](media/sql-server-agent-extension/install-sql-agent.png)

3. Выберите нужное расширение и **установите** его.
4. Выберите **Перезагрузить**, чтобы включить расширение (требуется только при первой установке расширения).
5. Перейдите на панель мониторинга управления, щелкнув сервер или базу данных правой кнопкой мыши и выбрав пункт **Управление**.
6. Установленные расширения отображаются в виде вкладок на панели мониторинга управления:

   ![Просмотр агента](media/sql-server-agent-extension/view-sql-agent.png)

## <a name="view-jobs"></a>Просмотр заданий

При подключении к расширению агента SQL Server первое, что вы увидите, — это список всех заданий агента.

   ![Просмотр заданий](media/sql-server-agent-extension/job-view.png)

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения об агенте SQL Server см. в [нашей документации](../../ssms/agent/sql-server-agent.md).
