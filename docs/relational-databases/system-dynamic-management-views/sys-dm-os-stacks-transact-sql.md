---
description: sys.dm_os_stacks (Transact-SQL)
title: sys.dm_os_stacks (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/13/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- dm_os_stacks
- dm_os_stacks_TSQL
- sys.dm_os_stacks
- sys.dm_os_stacks_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_os_stacks dynamic management view
ms.assetid: a69b06c4-28f0-4535-8fa1-9f132db4d916
author: WilliamDAssafMSFT
ms.author: wiassaf
monikerRange: =azuresqldb-current||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 27cc4ae0dd6629ab1801d79a19a1212b4e325ba6
ms.sourcegitcommit: 8dc7e0ececf15f3438c05ef2c9daccaac1bbff78
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2021
ms.locfileid: "100344306"
---
# <a name="sysdm_os_stacks-transact-sql"></a>sys.dm_os_stacks (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Это динамическое административное представление используется в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для следующих внутренних целей.  
  
-   Отслеживание отладочных данных, например необработанных запросов на выделение памяти;  
  
-   Установление или проверка логики, применяющейся компонентами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] там, где компонент предполагает определенный вызов.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**stack_address**|**varbinary(8)**|Уникальный адрес для данного размещения в стеке. Не допускает значение NULL.|  
|**frame_index**|**int**|Каждая строка представляет вызов функции, который при сортировке в возрастающем порядке по индексу кадра для конкретного **stack_address** возвращает полный стек вызовов. Не допускает значение NULL.|  
|**frame_address**|**varbinary(8)**|Адрес вызова функции. Не допускает значение NULL.|  
  
## <a name="remarks"></a>Remarks  
 **sys.dm_os_stacks** требует, чтобы символы сервера и другие компоненты присутствовали на сервере для правильного отображения информации.  
  
## <a name="permissions"></a>Разрешения

В [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] необходимо `VIEW SERVER STATE` разрешение.   
В базах данных SQL Basic, S0 и S1, а также для баз данных в эластичных пулах требуется учетная запись [администратора сервера](https://docs.microsoft.com/azure/azure-sql/database/logins-create-manage#existing-logins-and-user-accounts-after-creating-a-new-database) или учетная запись [администратора Azure Active Directory](https://docs.microsoft.com/azure/azure-sql/database/authentication-aad-overview#administrator-structure) . Для всех остальных целей службы базы данных SQL `VIEW DATABASE STATE` разрешение требуется в базе данных.   


## <a name="see-also"></a>См. также:  
  [SQL Server динамические административные представления, связанные с операционной системой &#40;&#41;Transact-SQL ](../../relational-databases/system-dynamic-management-views/sql-server-operating-system-related-dynamic-management-views-transact-sql.md)  
  
  
