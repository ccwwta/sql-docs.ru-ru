---
title: Наблюдение за использованием памяти
description: 'Мониторинг экземпляра SQL Server для подтверждения того, что память используется в допустимых пределах. Использование счетчиков "Память: доступно байт" и "Память: страниц/с".'
ms.custom: ''
ms.date: 01/20/2021
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- tuning databases [SQL Server], memory
- monitoring server performance [SQL Server], memory usage
- isolating memory [SQL Server]
- paging rate [SQL Server]
- memory [SQL Server], monitoring usage
- monitoring [SQL Server], memory usage
- low-memory conditions
- database monitoring [SQL Server], memory usage
- available memory [SQL Server]
- page faults [SQL Server]
- monitoring performance [SQL Server], memory usage
- server performance [SQL Server], memory
author: WilliamDAssafMSFT
ms.author: wiassaf
ms.openlocfilehash: 8954573b0c32eef45ec655b27d26e03e72be96ed
ms.sourcegitcommit: 713e5a709e45711e18dae1e5ffc190c7918d52e7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "98688774"
---
# <a name="monitor-memory-usage"></a>Наблюдение за использованием памяти
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  Проводите периодический мониторинг экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для подтверждения того, что память используется в допустимых пределах. 

## <a name="configuring-ssnoversion-max-memory"></a>Настройка максимального размера памяти для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]

По умолчанию экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может со временем использовать большую часть памяти, доступной операционной системе Windows на сервере. После занятия памяти она не высвобождается, пока не будет обнаружена нехватка памяти. Такое поведение является нормальным и не свидетельствует об утечке памяти в процессе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Чтобы ограничить объем памяти, который сервер [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может использовать в своих целях, задайте [параметр **max server memory**](../../database-engine/configure-windows/server-memory-server-configuration-options.md). Дополнительные сведения см. в статье [Руководство по архитектуре управления памятью](../../relational-databases/memory-management-architecture-guide.md#changes-to-memory-management-starting-with-).

В SQL Server на Linux [установить ограничение памяти](../../linux/sql-server-linux-performance-best-practices.md#advanced-configuration) можно с помощью средства mssql-conf и [параметра memory.memorylimitmb](../../linux/sql-server-linux-configure-mssql-conf.md#memorylimit).  

## <a name="monitor-operating-system-memory"></a>Наблюдение за памятью операционной системы   
 Для отслеживания нехватки памяти используйте приведенные ниже счетчики Windows. Значения многих счетчиков памяти операционной системы можно запрашивать с помощью динамических административных представлений [sys.dm_os_process_memory](../system-dynamic-management-views/sys-dm-os-process-memory-transact-sql.md) и [sys.dm_os_sys_memory](../system-dynamic-management-views/sys-dm-os-sys-memory-transact-sql.md).

-   **Память: доступно байтов**  
Этот счетчик указывает на то, сколько байт памяти доступно на данный момент для использования процессами. Низкие значения счетчика **Доступно байтов** могут указывать на общую нехватку памяти операционной системы. Это значение можно запросить с помощью T-SQL из [sys.dm_os_sys_memory](../system-dynamic-management-views/sys-dm-os-sys-memory-transact-sql.md).available_physical_memory_kb.

-   **Память: страниц/с**  
Этот счетчик показывает число страниц, которые были или получены с диска из-за ошибок страниц физической памяти, или записаны на диск для освобождения пространства в рабочем множестве из-за ошибок страниц. Большое значение счетчика **Страниц/с** может означать излишнюю подкачку.  

-   **Память: ошибок страницы/с** Этот счетчик показывает частоту ошибок страниц для всех процессов, включая системные. Низкий, но не нулевой уровень выгрузки на диск (и вызванные ею ошибки страниц) является нормальным, даже если у компьютера достаточно большое количество доступной памяти. Диспетчер виртуальной памяти (VMM) Microsoft Windows берет страницы из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и других процессов по мере того, как он урезает размеры рабочих множеств этих процессов. Деятельность VMM может привести к ошибкам страниц.  

-   **Процесс: ошибок страницы/с** Этот счетчик показывает частоту ошибок страниц для определенного пользовательского процесса. С помощью счетчика **Процесс: ошибок страниц/с** можно определить, вызвана ли повышенная активность диска подкачкой, выполняемой сервером [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Чтобы определить, является ли [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или другой процесс причиной излишней подкачки, наблюдайте за счетчиком **Процесс: ошибок страниц/с** для экземпляра процесса [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 Дополнительные сведения об устранении проблемы излишней подкачки см. в документации по операционной системе.  
  
## <a name="isolating-memory-used-by-ssnoversion"></a>Изоляция памяти, используемой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 

 Для мониторинга использования памяти сервером [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используйте приведенные ниже [счетчики объектов SQL Server](use-sql-server-objects.md). Значения многих счетчиков объектов SQL Server можно запрашивать с помощью динамических административных представлений [sys.dm_os_performance_counters](../system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql.md) и [sys.dm_os_process_memory](../system-dynamic-management-views/sys-dm-os-process-memory-transact-sql.md).

 По умолчанию сервер [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] управляет требованиями к памяти динамически исходя из доступных ресурсов системы. Если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] нужно больше памяти, он производит запрос к операционной системе, чтобы определить, доступна ли свободная физическая память, и использует ее. Если в операционной системе недостаточно свободной памяти, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] будет освобождать память для операционной системы до тех пор, пока нехватка памяти не будет устранена или пока [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не достигнет предела **min server memory**. Однако можно отказаться от динамического использования памяти, задав значения для параметров конфигурации сервера **min server memory** и **max server memory**. Дополнительные сведения см. в разделе [Параметры памяти сервера](../../database-engine/configure-windows/server-memory-server-configuration-options.md).  
  
 Для мониторинга объема памяти, используемого [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , наблюдайте за следующими счетчиками производительности.  
  
-   **SQL Server: Memory Manager: общая память сервера (КБ)**  
Этот счетчик показывает объем памяти операционной системы, выделенной в настоящее время серверу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] диспетчером памяти [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Данное значение, как правило, увеличивается при повышении активности и растет после запуска SQL Server. Получить этот счетчик можно из столбца **committed_kb** динамического административного представления [sys.dm_os_sys_info](../system-dynamic-management-views/sys-dm-os-sys-info-transact-sql.md).

-   **SQL Server: Memory Manager: память целевого сервера (КБ)**  
Этот счетчик показывает идеальный объем памяти для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в соответствии с рабочей нагрузкой за последнее время. Чтобы определить, выделен ли для сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] оптимальный объем памяти, сравните это значение со счетчиком **Общая память сервера** по истечении некоторого периода работы со стандартной нагрузкой. Значения счетчиков **Общая память сервера** и **Память целевого сервера** должны быть примерно равны. Если значение **Общая память сервера** значительно меньше, чем значение **Память целевого сервера**, возможно, экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не хватает памяти. Через некоторое время после запуска [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] значение **Общая память сервера** возрастает. При этом значение **Память целевого сервера** должно быть больше, чем **Общая память сервера**. Получить этот счетчик можно из столбца **committed_target_kb** динамического административного представления [sys.dm_os_sys_info](../system-dynamic-management-views/sys-dm-os-sys-info-transact-sql.md). Дополнительные сведения и рекомендации по настройке памяти см. в статье [Параметры конфигурации памяти сервера](../../database-engine/configure-windows/server-memory-server-configuration-options.md#manually).

-   **Процесс: рабочий набор**  
Этот счетчик показывает объем физической памяти, используемой процессом в настоящее время, согласно данным операционной системы. Обратите внимание на экземпляр этого счетчика для sqlservr.exe. Получить этот счетчик можно из столбца **physical_memory_in_use_kb** динамического административного представления [sys.dm_os_process_memory](../system-dynamic-management-views/sys-dm-os-process-memory-transact-sql.md).

-   **Процесс: байт исключительного пользования**  
Этот счетчик показывает объем памяти операционной системы, запрошенный процессом для использования в собственных целях. Обратите внимание на экземпляр этого счетчика для sqlservr.exe. Так как этот счетчик учитывает все выделения памяти, запрошенные процессом sqlservr.exe, включая выходящие за пределы [**max server memory**](../../database-engine/configure-windows/server-memory-server-configuration-options.md), его значение может превышать значение [параметра **max server memory**](../../database-engine/configure-windows/server-memory-server-configuration-options.md).

-   **SQL Server: Buffer Manager: страниц базы данных**  
Этот счетчик указывает число страниц с содержимым базы данных в буферном пуле. Память, не относящаяся к буферному пулу процесса SQL Server, не учитывается. Запросить этот счетчик можно из динамического административного представления [sys.dm_os_performance_counters](../system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql.md).

-   **SQL Server: Buffer Manager: коэффициент попаданий в буферный кэш**  
Этот счетчик относится только к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Желательно, чтобы коэффициент был не меньше 90. Значение выше 90 указывает на то, что более 90 процентов всех запрошенных данных были получены из кэша данных в памяти без считывания с диска. Дополнительные сведения о диспетчере буферов SQL Server см. в статье [SQL Server, объект Buffer Manager](sql-server-buffer-manager-object.md). Запросить этот счетчик можно из динамического административного представления [sys.dm_os_performance_counters](../system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql.md).  
 
-   **SQL Server: Buffer Manager: ожидаемое время существования страницы**  
Этот счетчик измеряет, сколько секунд самая старая страница находится в буферном пуле. Для систем с архитектурой NUMA это среднее значение для всех узлов NUMA. Чем больше это значение, тем лучше. Его резкое падение указывает на постоянное обновление данных в буферном пуле, из-за которого рабочая нагрузка недостаточно эффективно использует данные, уже находящиеся в памяти. У каждого узла NUMA имеется собственный узел буферного пула. На серверах с несколькими узлами NUMA узнать ожидаемое время существования страницы для каждого узла буферного пула можно с помощью счетчика **SQL Server: узел буфера: ожидаемое время существования страницы**. Запросить этот счетчик можно из динамического административного представления [sys.dm_os_performance_counters](../system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql.md).

  
## <a name="examples"></a>Примеры 

### <a name="determining-current-memory-allocation"></a>Определение текущего распределения памяти  
 Приведенные ниже запросы возвращают сведения о текущем распределении памяти.  
  
```  
SELECT
(total_physical_memory_kb/1024) AS Total_OS_Memory_MB,
(available_physical_memory_kb/1024)  AS Available_OS_Memory_MB
FROM sys.dm_os_sys_memory;

SELECT  
(physical_memory_in_use_kb/1024) AS Memory_used_by_Sqlserver_MB,  
(locked_page_allocations_kb/1024) AS Locked_pages_used_by_Sqlserver_MB,  
(total_virtual_address_space_kb/1024) AS Total_VAS_in_MB,
process_physical_memory_low,  
process_virtual_memory_low  
FROM sys.dm_os_process_memory;  
```  

### <a name="determining-current-sql-server-memory-utilization"></a>Определение текущего объема памяти, используемого сервером SQL Server   
 Приведенный ниже запрос возвращает сведения о текущем использовании памяти сервером SQL Server.  
```  
SELECT
sqlserver_start_time,
(committed_kb/1024) AS Total_Server_Memory_MB,
(committed_target_kb/1024)  AS Target_Server_Memory_MB
FROM sys.dm_os_sys_info;
```   

### <a name="determining-page-life-expectancy"></a>Определение ожидаемого времени существования страницы
 В приведенном ниже запросе с помощью представления **sys.dm_os_performance_counters** отслеживается текущее значение **ожидаемого времени существования страницы** для экземпляра SQL Server на уровне как всего диспетчера буферов, так и каждого узла NUMA.
```
SELECT
CASE instance_name WHEN '' THEN 'Overall' ELSE instance_name END AS NUMA_Node, cntr_value AS PLE_s
FROM sys.dm_os_performance_counters    
WHERE counter_name = 'Page life expectancy';
```

## <a name="see-also"></a>См. также
- [sys.dm_os_sys_memory (Transact-SQL)](../system-dynamic-management-views/sys-dm-os-sys-memory-transact-sql.md)
- [sys.dm_os_process_memory (Transact-SQL)](../system-dynamic-management-views/sys-dm-os-process-memory-transact-sql.md)
- [sys.dm_os_sys_info (Transact-SQL)](../system-dynamic-management-views/sys-dm-os-sys-info-transact-sql.md)
- [sys.dm_os_performance_counters (Transact-SQL)](../system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql.md)
- [SQL Server, объект Memory Manager](sql-server-memory-manager-object.md)
- [SQL Server, объект Buffer Manager](sql-server-buffer-manager-object.md)   
- [Параметры конфигурации памяти сервера](../../database-engine/configure-windows/server-memory-server-configuration-options.md)
- [Руководство по архитектуре управления памятью](../../relational-databases/memory-management-architecture-guide.md)
