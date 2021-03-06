---
title: Пул ресурсов регулятора ресурсов
description: SQL Server Resource Governor задает ограничения на загрузку ЦП, физических операций ввода-вывода и использование памяти, которые доступны для входящих запросов приложений в пуле ресурсов.
ms.custom: ''
ms.date: 10/20/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, resource pool
- resource pool [SQL Server], overview
- resource pool [SQL Server]
ms.assetid: 306b6278-e54f-42e6-b746-95a9315e0cbe
author: WilliamDAssafMSFT
ms.author: wiassaf
ms.openlocfilehash: 065cf98e5ada04d4ac192c50f4c5b5a3d1790bf6
ms.sourcegitcommit: b1cec968b919cfd6f4a438024bfdad00cf8e7080
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2021
ms.locfileid: "99237360"
---
# <a name="resource-governor-resource-pool"></a>Пул ресурсов регулятора ресурсов
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

  В регуляторе ресурсов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] пул ресурсов представляет подмножество физических ресурсов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]. Регулятор ресурсов позволяет задать ограничения на загрузку ЦП, физических средств ввода-вывода и использование памяти, которые доступны для входящих запросов приложений в пуле ресурсов. Каждый пул ресурсов может содержать одну или несколько групп рабочей нагрузки. После запуска сеанса классификатор регулятора ресурсов назначает этот сеанс группе рабочей нагрузки и этот сеанс должен функционировать с ресурсами, назначенными этой группе рабочей нагрузки.  
  
## <a name="resource-pool-concepts"></a>Понятия пула ресурсов  
 Пул ресурсов (или пул) представляет физические ресурсы сервера. Пул можно считать виртуальным экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] внутри экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Пул состоит из двух компонентов. Один из них не взаимодействует с другими пулами, что обеспечивает минимальное резервирование ресурсов. Другой компонент является общим с другими пулами, что поддерживает максимально возможное потребление ресурсов. Ресурсы пула определяются указанием одного или нескольких следующих параметров для каждого ресурса (ЦП, память и физический ввод-вывод).  
  
-   **MIN_CPU_PERCENT и MAX_CPU_PERCENT**  
  
     Эти параметры — минимальная и максимальная гарантированная средняя пропускная способность ЦП для всех запросов в пуле ресурсов при возникновении состязания за ЦП. Можно использовать эти параметры для задания прогнозируемого использования ресурсов ЦП для нескольких рабочих нагрузок в зависимости от потребностей каждой рабочей нагрузки. Например, предположим, что отделы продаж и маркетинга компании пользуются одной и той же базой данных. Отдел продаж использует рабочую нагрузку с высокой нагрузкой на ЦП и самыми важными запросами. У отдела маркетинга рабочая нагрузка на ЦП также высока, но имеет более низкий приоритет. Создав отдельный пул ресурсов для каждого отдела, можно установить *минимальный* процент использования ЦП для пула ресурсов отдела продаж в значение 70, а *максимальный* процент использования ЦП для пула ресурсов отдела маркетинга — в значение 30. Это гарантирует, что рабочая нагрузка отдела продаж получит необходимые ей ресурсы ЦП, а рабочая нагрузка отдела маркетинга будет изолирована от требований к ЦП рабочей нагрузки отдела продаж. Обратите внимание, что максимальный процент использования ЦП — это уступающий максимум. При наличии доступной производительности ЦП рабочая нагрузка использует ее до 100 процентов. Максимальное значение применяется только при возникновении состязания за ресурсы ЦП. В этом примере, если рабочая нагрузка отдела продаж отключена, рабочая нагрузка отдела маркетинга может использовать 100 процентов ЦП при необходимости.  
  
-   **CAP_CPU_PERCENT**  
  
     Параметр CAP_CPU_PERCENT — это жесткое ограничение на пропускную способность ЦП для всех запросов в пуле ресурсов. Рабочие нагрузки, связанные с этим пулом, могут использовать производительность ЦП выше значения MAX_CPU_PERCENT, если она доступна, но не превышать CAP_CPU_PERCENT. В приведенном выше примере предположим, что с отдела маркетинга взимается плата за использование ресурсов. Они хотят иметь прогнозируемое выставление счетов и не хотят платить за более чем 30 процентов ЦП. Это выполняется путем установки CAP_CPU_PERCENT в значение 30 для пула ресурсов отдела маркетинга.  
  
-   **MIN_MEMORY_PERCENT и MAX_MEMORY_PERCENT**  
  
     Эти параметры указывают минимальный и максимальный объемы памяти, резервируемые для данного пула ресурсов, который не подлежит использованию совместно с другими пулами ресурсов. В случае баз данных с таблицами, оптимизированными для памяти, подразумевается доступная для выполнения запросов память, а не память буферного пула (например, страниц данных и индексов). Установка минимального значения памяти для пула дает гарантию того, что указанный процент памяти будет доступен для всех запросов, которые могут выполняться в этом пуле ресурсов. Это важное различие по сравнению с MIN_CPU_PERCENT, поскольку в этом случае память может оставаться в данном пуле ресурсов, даже если пул не имеет запросов в группах рабочей нагрузки, принадлежащих к нему. Поэтому очень важно крайне внимательно использовать этот параметр, поскольку эта память будет недоступна для любого другого пула, даже если активных запросов нет. Максимальное значение памяти для пула означает, что запросы, выполняемые в этом пуле, никогда не получат больше данной доли общей памяти.

     Чтобы управлять с помощью Resource Governor памятью для таблиц, оптимизированных для памяти, необходимо привязать базу данных к отдельному пулу ресурсов. Дополнительные сведения см. в статье [Привязка базы данных с таблицами, оптимизированными для памяти, к пулу ресурсов](../in-memory-oltp/bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md).
  
-   **AFFINITY**  
  
     Этот параметр позволяет привязать пул ресурсов к одному или нескольким планировщикам или узлам NUMA для еще большей изоляции ресурсов ЦП. В вышеупомянутом сценарии с отделами продаж и маркетинга предположим, что отделу продаж требуется более изолированная среда и необходимо 100 процентов ядра ЦП постоянно. С помощью параметра AFFINITY рабочие нагрузки отделов продаж и маркетинга могут быть назначены на разные процессоры. Если параметр CAP_CPU_PERCENT для пула маркетинга остается на месте, рабочая нагрузка отдела маркетинга продолжает использовать не более 30 процентов одного ядра, а рабочая нагрузка отдела продаж использует 100 процентов другого ядра. Рабочие нагрузки отделов продаж и маркетинга фактически выполняются на 2 изолированных компьютерах.  
  
-   **MIN_IOPS_PER_VOLUME и MAX_IOPS_PER_VOLUME**  
  
     Эти параметры задают минимум и максимум физических операций ввода-вывода в секунду на том диска для пула ресурсов. Эти параметры можно использовать для управления физическими операциями ввода-вывода, предоставленными для пользовательских потоков для данного пула ресурсов. Например, отдел продаж создает несколько отчетов в конце месяца большими пакетами. Запросы в этих пакетах могут вызывать операции ввода-вывода, которые могут насытить дисковый объем и повлиять на производительность других рабочих нагрузок с более высоким приоритетом в базе данных. Для изолирования этой рабочей нагрузки можно установить MIN_IOPS_PER_VOLUME в 20 и MAX_IOPS_PER_VOLUME в 100 для пула ресурсов отдела продаж, что задаст уровень ввода-вывода, предоставляемый рабочей нагрузке.  
  
При настройке процессора или памяти сумма значений MIN всех пулов не может превышать 100 % ресурсов сервера. Кроме того, при настройке ЦП и памяти значения MAX и END могут быть установлены в пределах от значения MIN до 100 включительно.  
  
Если в пуле определено ненулевое значение MIN, то эффективное значение MAX других пулов переопределяется. Из 100 процентов вычитается минимальное настроенное значение MAX для пула и сумма значений MIN других пулов.  
  
Некоторые основные понятия, описанные выше, проиллюстрированы в следующей таблице. В таблице показаны параметры внутреннего пула, пула по умолчанию и двух определяемых пользователем пулов. 
  
|Имя пула|Параметр MIN, %|Параметр MAX, %|Вычисляемое эффективное значение MAX, %|Вычисляемый общий %|Комментарий|  
|---------------|-------------------|-------------------|--------------------------------|-------------------------|-------------|  
|Внутренние|0|100|100|0|Фактическое значение MAX% и shared% неприменимы к внутреннему пулу.|  
|значение по умолчанию|0|100|30|30|Эффективное значение MAX вычисляется следующим образом: min(100,100-(20+50)) = 30. Вычисляемый общий процентный показатель — это фактическое значение MAX - MIN = 30.|  
|Пул 1|20|100|50|30|Эффективное значение MAX вычисляется так: min(100,100-50)=50. Вычисляемый общий процентный показатель — это фактическое значение MAX - MIN = 30.|  
|Пул 2|50|70|70|20|Эффективное значение MAX вычисляется так: min(70,100-20)=70. Вычисляемый общий процентный показатель — это эффективное значение MAX-MIN=20.|  

Приведенные ниже формулы используются для вычисления фактического значения MAX% и общего процентного показателя в таблице выше.  
  
-   Min(X,Y) — это наименьшие значения X и Y.  
  
-   Sum(X) — это сумма значений X всех пулов.  
  
-   Всего общих % = 100 - sum(MIN %).  
  
-   Фактическое значение MAX % = min(X,Y).  
  
-   Общие % = фактическое значение MAX % - MIN %.  

Пользуясь приведенной выше таблицей в качестве примера, можно далее проиллюстрировать изменения, которые вносятся при создании еще одного пула. Этот пул — Пул 3, имеющий значение MIN %, равное 5.  
  
|Имя пула|Параметр MIN, %|Параметр MAX, %|Вычисляемое эффективное значение MAX, %|Вычисляемый общий %|Комментарий|  
|---------------|-------------------|-------------------|--------------------------------|-------------------------|-------------|  
|Внутренние|0|100|100|0|Фактическое значение MAX% и shared% неприменимы к внутреннему пулу.|  
|значение по умолчанию|0|100|25|25|Эффективное значение MAX вычисляется следующим образом: min(100,100-(20+50+5)) = 25. Вычисляемый общий процентный показатель — это фактическое значение MAX - MIN = 25.|  
|Пул 1|20|100|45|25|Эффективное значение MAX вычисляется так: min(100,100-55)=45. Вычисляемый общий процентный показатель — это фактическое значение MAX - MIN = 25.|  
|Пул 2|50|70|70|20|Эффективное значение MAX вычисляется следующим образом: min(70,100-25) = 70. Вычисляемый общий процентный показатель — это эффективное значение MAX-MIN=20.|  
|Пул 3|5|100|30|25|Эффективное значение MAX вычисляется следующим образом: min(100,100-70) = 30. Вычисляемый общий процентный показатель — это фактическое значение MAX - MIN = 25.|  
  
 Общая часть пула показывает, куда могут помещаться доступные ресурсы, если они есть. Однако при потреблении ресурсов они помещаются в указанный пул и не являются общими. Это позволяет более рационально использовать ресурсы в тех случаях, когда отсутствуют запросы в данный пул, и ресурсы, соответствующие этому пулу, можно сделать доступными для остальных пулов.  
  
 Ниже приведены особые случаи конфигурации пулов.  
  
-   Во всех пулах заданы минимумы, которые в сумме дают 100% ресурсов сервера. В этом случае фактические максимумы равны минимумам. Это аналогично разделению ресурсов сервера на непересекающиеся области независимо от потребления ресурсов внутри любого пула.  
  
-   У всех пулов минимумы равны нулю. Все пулы конкурируют за доступные ресурсы, и их окончательный размер основан на потреблении ресурсов в каждом пуле. В формировании окончательного размера пула также играют роль другие факторы, например политики.  
  
В регуляторе ресурсов есть два стандартных пула ресурсов: внутренний пул и пул по умолчанию. Можно добавить дополнительные пулы.  
  
**Внутренний пул**  
  
Внутренний пул представляет ресурсы, используемые самим [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Этот пул всегда содержит только внутреннюю группу, и пул нельзя изменить никаким способом. Потребление ресурсов во внутреннем пуле не ограничивается. Любая рабочая нагрузка в пуле рассматривается как критическая для работы сервера, и регулятор ресурсов позволяет внутреннему пулу передавать нагрузку на другие пулы, даже если это приводит к нарушению ограничений, заданных для этих пулов.  
  
> [!NOTE]  
>  Потребление ресурсов внутреннего пула и внутренней группы не вычитается из общего потребления ресурсов. Процентные показатели вычисляются на основе общего объема доступных ресурсов.  
  
**Пул по умолчанию**  
  
Пул по умолчанию — это первый стандартный пользовательский пул. До какой-либо настройки пул по умолчанию содержит только группу по умолчанию. Пул по умолчанию нельзя создать или удалить, но его можно изменить. Пул по умолчанию может содержать определяемые пользователем группы в дополнение к группе по умолчанию. Начиная с версии [!INCLUDE[sssql16-md](../../includes/sssql16-md.md)] доступны такие пулы ресурсов по умолчанию: пул для стандартных операций [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и пул для внешних процессов, например для выполнения R-скриптов.  
  
> [!NOTE]  
>  Группу по умолчанию можно изменить, но ее нельзя переместить за пределы пула по умолчанию.  
  
**Внешний пул**  
  
Пользователи могут определить внешний пул, чтобы определить ресурсы для внешних процессов. В отношении служб R он применяется для `rterm.exe`, `BxlServer.exe` и порожденных ими процессов.  
  
**Определяемые пользователем пулы ресурсов**  
  
Определяемые пользователем пулы ресурсов — это пулы ресурсов, создаваемые для конкретных рабочих нагрузок в вашей среде. В регуляторе ресурсов предусмотрены инструкции DDL для создания, изменения и удаления пулов ресурсов.  
  
## <a name="resource-pool-tasks"></a>Задачи пула ресурсов  
  
|Описание задачи|Статья|  
|----------------------|-----------|  
|Описывает процесс создания пула ресурсов.|[Создание пула ресурсов](../../relational-databases/resource-governor/create-a-resource-pool.md)|  
|Описывает, как изменить параметры пула ресурсов.|[Изменение параметров пула ресурсов](../../relational-databases/resource-governor/change-resource-pool-settings.md)|  
|Описывает, как удалить пул ресурсов.|[Удаление пула ресурсов](../../relational-databases/resource-governor/delete-a-resource-pool.md)|  
  
## <a name="see-also"></a>См. также:  
 [регулятор ресурсов](../../relational-databases/resource-governor/resource-governor.md)   
 [Группа рабочей нагрузки регулятора ресурсов](../../relational-databases/resource-governor/resource-governor-workload-group.md)   
 [Функция-классификатор регулятора ресурсов](../../relational-databases/resource-governor/resource-governor-classifier-function.md)   
 [Настройка регулятора ресурсов с помощью шаблона](../../relational-databases/resource-governor/configure-resource-governor-using-a-template.md)   
 [Просмотр свойств регулятора ресурсов](../../relational-databases/resource-governor/view-resource-governor-properties.md)  
  
  
