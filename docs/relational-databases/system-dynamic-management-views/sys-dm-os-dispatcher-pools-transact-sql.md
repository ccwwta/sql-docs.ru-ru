---
description: sys.dm_os_dispatcher_pools (Transact-SQL)
title: sys.dm_os_dispatcher_pools (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 08/18/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- dm_os_dispatcher_pools_TSQL
- dm_os_dispatcher_pools
- sys.dm_os_dispatcher_pools
- sys.dm_os_dispatcher_pools_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- extended events [SQL Server], views
- sys.dm_os_dispatcher_pools DMV
ms.assetid: b9edbc83-c6bc-4753-9bb5-a454cfe7d6bf
author: WilliamDAssafMSFT
ms.author: wiassaf
ms.openlocfilehash: dcd6c612f406e3c4ae10c7ab0aacfeb3a71fd9c9
ms.sourcegitcommit: 8dc7e0ececf15f3438c05ef2c9daccaac1bbff78
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2021
ms.locfileid: "100338877"
---
# <a name="sysdm_os_dispatcher_pools-transact-sql"></a>sys.dm_os_dispatcher_pools (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Возвращает сведения о пулах диспетчера сеансов. Пулы диспетчеров представляют собой пулы потоков, используемые системными компонентами для фоновой обработки.  
  
> [!NOTE]  
>  Чтобы вызвать эту функцию из [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] или [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] , используйте имя **sys.dm_pdw_nodes_os_dispatcher_pools**.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|dispatcher_pool_address|**varbinary(8)**|Адрес пула диспетчеров. dispatcher_pool_address является уникальным. Не допускает значение NULL.|  
|тип|**nvarchar(256)**|Тип пула диспетчеров. Не допускает значение NULL. Существует два типа пулов диспетчеров:<br /><br /> DISP_POOL_XE_ENGINE;<br /><br /> DISP_POOL_XE_SESSION.<br /><br /> Запрос к динамическому административному представлению для полного списка|  
|name|**nvarchar(256)**|Имя пула диспетчеров. Не допускает значение NULL.|  
|dispatcher_count|**int**|Число активных потоков диспетчеров. Не допускает значение NULL.|  
|dispatcher_ideal_count|**int**|Число потоков диспетчеров, которые могут быть задействованы по мере роста пула диспетчеров. Не допускает значение NULL.|  
|dispatcher_timeout_ms|**int**|Время в миллисекундах, в течение которого диспетчер будет ожидать нового задания, прежде чем завершить работу. Не допускает значение NULL.|  
|dispatcher_waiting_count|**int**|Число бездействующих потоков диспетчеров. Не допускает значение NULL.|  
|queue_length|**int**|Число рабочих элементов, ожидающих обработки пулом диспетчеров. Не допускает значение NULL.|  
|pdw_node_id|**int**|**Применимо к**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] , [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]<br /><br /> Идентификатор узла, на котором находится данное распределение.|  
  
## <a name="permissions"></a>Разрешения

В [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] необходимо `VIEW SERVER STATE` разрешение.   
В базах данных SQL Basic, S0 и S1, а также для баз данных в эластичных пулах требуется учетная запись [администратора сервера](https://docs.microsoft.com/azure/azure-sql/database/logins-create-manage#existing-logins-and-user-accounts-after-creating-a-new-database) или учетная запись [администратора Azure Active Directory](https://docs.microsoft.com/azure/azure-sql/database/authentication-aad-overview#administrator-structure) . Для всех остальных целей службы базы данных SQL `VIEW DATABASE STATE` разрешение требуется в базе данных.   

## <a name="see-also"></a>См. также  
  
  


