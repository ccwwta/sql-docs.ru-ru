---
title: Настройка стандартных предупреждений репликации (SSMS)
description: Узнайте, как настроить стандартные предупреждения репликации с помощью среды SQL Server Management Studio (SSMS).
ms.custom: seo-lt-2019
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server replication]
- predefined replication alerts [SQL Server replication]
ms.assetid: c0414147-7ffe-4f9a-908c-71c1b5201584
author: MashaMSFT
ms.author: mathoma
monikerRange: =azuresqldb-mi-current||>=sql-server-2016
ms.openlocfilehash: fa85c871d8fd1cc8ade0ed0a1b0a41e8e596fee7
ms.sourcegitcommit: 1a544cf4dd2720b124c3697d1e62ae7741db757c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2020
ms.locfileid: "97439875"
---
# <a name="configure-predefined-replication-alerts-sql-server-management-studio"></a>Настройка стандартных предупреждений репликации (среда SQL Server Management Studio)
[!INCLUDE[applies-to-version/_ssnoversion.md](../../../includes/applies-to-version/sqlserver.md)]
  Репликация предоставляет следующие предварительно установленные предупреждения, которые могут быть настроены для реакции на события репликации:  
  
-   **Репликация: успех агента**  
  
-   **Репликация: неудача агента**  
  
-   **Репликация: повторная попытка агента**  
  
-   **Репликация: истекшая подписка удалена**  
  
-   **Репликация: подписка повторно инициализирована после неудачной проверки**  
  
-   **Репликация: подписчик не прошел проверку данных**  
  
-   **Репликация: подписчик прошел проверку данных**  
  
-   **Репликация: нестандартное завершение работы агента**  
  
 Настройте эти предупреждения в папке **Предупреждения** среды [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или на вкладке **Предупреждения** монитора репликации. Дополнительные сведения о доступе к этой вкладке см. в статье [Просмотр сведений и выполнение задач с помощью монитора репликации](../../../relational-databases/replication/monitor/view-information-and-perform-tasks-replication-monitor.md).  
  
 Наряду с этими предупреждениями монитор репликации предоставляет набор предупреждений и оповещений, относящихся к состоянию и производительности. Дополнительные сведения см. в статье [Set Thresholds and Warnings in Replication Monitor](../../../relational-databases/replication/monitor/set-thresholds-and-warnings-in-replication-monitor.md). Можно также определить предупреждения для других событий репликации при помощи инфраструктуры предупреждений [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . Дополнительные сведения см. в статье [Создание пользовательского события](../../../ssms/agent/create-a-user-defined-event.md).  
  
### <a name="to-configure-a-predefined-replication-alert-in-management-studio"></a>Настройка предварительно определенного предупреждения репликации в Management Studio  
  
1.  Подключитесь к распространителю в [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]и разверните узел сервера.  
  
2.  Раскройте папку **Агент SQL Server** , затем раскройте папку **Предупреждения** .  
  
3.  Щелкните правой кнопкой мыши предупреждение репликации, затем щелкните **Свойства**.  
  
4.  Задайте следующие параметры в диалоговом окне **\<AlertName> свойств предупреждения**.  
  
    -   На странице **Общие** щелкните **Включить**, укажите базу данных, к которой нужно применить данное предупреждение.  
  
    -   На странице **Ответ** укажите, надо ли отправить оповещение по электронной почте и/или запустить задание.  
  
         Если появилось предупреждение **Репликация: ошибка проверки данных подписчиком**, можно указать ответное задание, которое предусмотрено в репликации для этого предупреждения. Выберите **Выполнить задание** и нажмите кнопку обзора ( **…** ). В диалоговом окне **Найти задание** щелкните **Обзор**. В диалоговом окне **Поиск объектов** установите флажок **Повторная инициализация подписок, имеющих сбои при выполнении проверки данных**. В обоих окнах нажмите **ОК** . Во время выполнения задание осуществляет удаленный вызов хранимой процедуры, которая повторно инициализирует подписку. Если издатель использует удаленный распространитель, необходимо указать на издателе имя входа удаленного сервера, чтобы сделать возможным удаленный вызов процедур с распространителя на издатель.  
  
    -   На странице **Параметры** измените текст ответа.  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

### <a name="to-configure-an-alert-for-a-threshold-in-replication-monitor"></a>Настройка предупреждения для порогового значения в мониторе репликации  
  
1.  На вкладке **Предупреждения** щелкните **Настройка предупреждений**.  
  
2.  В диалоговом окне **Настройка предупреждений репликации** выберите необходимое предупреждение, а затем щелкните **Настроить**.  
  
3.  Задайте следующие параметры в диалоговом окне **\<AlertName> свойств предупреждения**.  
  
    -   На странице **Общие** щелкните **Включить**, укажите базу данных, к которой нужно применить данное предупреждение.  
  
    -   На странице **Ответ** укажите, надо ли отправить оповещение по электронной почте и/или запустить задание.  
  
         Если появилось предупреждение **Репликация: ошибка проверки данных подписчиком**, можно указать ответное задание, которое предусмотрено в репликации для этого предупреждения. Выберите **Выполнить задание** и нажмите кнопку обзора ( **…** ). В диалоговом окне **Найти задание** щелкните **Обзор**. В диалоговом окне **Поиск объектов** установите флажок **Повторная инициализация подписок, имеющих сбои при выполнении проверки данных**. В обоих окнах нажмите **ОК** . Во время выполнения задание осуществляет удаленный вызов хранимой процедуры, которая повторно инициализирует подписку. Если издатель использует удаленный распространитель, необходимо указать на издателе имя входа удаленного сервера, чтобы сделать возможным удаленный вызов процедур с распространителя на издатель.  
  
    -   На странице **Параметры** измените текст ответа.  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  Щелкните **Закрыть**.  
  
## <a name="see-also"></a>См. также:  
 [Использование предупреждений для событий агента репликации](../../../relational-databases/replication/agents/use-alerts-for-replication-agent-events.md)  
  
