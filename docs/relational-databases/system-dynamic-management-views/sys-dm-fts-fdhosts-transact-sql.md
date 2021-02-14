---
description: sys.dm_fts_fdhosts (Transact-SQL)
title: sys.dm_fts_fdhosts (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/29/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- dm_fts_fdhosts
- dm_fts_fdhosts_TSQL
- sys.dm_fts_fdhosts
- sys.dm_fts_fdhosts_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_fts_fdhosts dynamic management view
- troubleshooting [SQL Server], full-text search
ms.assetid: d42a6334-4362-4361-83da-f8324fe55ec7
author: pmasl
ms.author: pelopes
monikerRange: =azuresqldb-current||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: d88fd09206405e9cc277f83d42a385a7e1542b5c
ms.sourcegitcommit: 8dc7e0ececf15f3438c05ef2c9daccaac1bbff78
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2021
ms.locfileid: "100345343"
---
# <a name="sysdm_fts_fdhosts-transact-sql"></a>sys.dm_fts_fdhosts (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Возвращает сведения о текущем действии узла управляющей программы фильтрации или узлов на экземпляре сервера.  
  
 
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**fdhost_id**|**int**|Идентификатор узла управляющей программы фильтрации.|  
|**fdhost_name**|**nvarchar(120)**|Имя узла управляющей программы фильтрации.|  
|**fdhost_process_id**|**int**|Идентификатор процесса Windows узла управляющей программы фильтрации.|  
|**fdhost_type**|**nvarchar(120)**|Тип документа, обрабатываемого узлом управляющей программы фильтрации, — один из следующих.<br /><br /> Одиночный поток.<br /><br /> Многопоточный.<br /><br /> Огромный документ.|  
|**max_thread**|**int**|Максимальное количество потоков в узле управляющей программы фильтрации.|  
|**batch_count**|**int**|Количество пакетов, обрабатываемых в узле управляющей программы фильтрации.|  
  
## <a name="permissions"></a>Разрешения  

В [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] необходимо `VIEW SERVER STATE` разрешение.   
В базах данных SQL Basic, S0 и S1, а также для баз данных в эластичных пулах требуется учетная запись [администратора сервера](https://docs.microsoft.com/azure/azure-sql/database/logins-create-manage#existing-logins-and-user-accounts-after-creating-a-new-database) или учетная запись [администратора Azure Active Directory](https://docs.microsoft.com/azure/azure-sql/database/authentication-aad-overview#administrator-structure) . Для всех остальных целей службы базы данных SQL `VIEW DATABASE STATE` разрешение требуется в базе данных.   

## <a name="examples"></a>Примеры  
 В следующем примере возвращается имя узла управляющей программы фильтрации и максимальное число потоков в ней. Также отслеживается текущее количество пакетов, одновременно обрабатываемых в управляющей программе фильтрации. Эти сведения могут использоваться для диагностики производительности.  
  
```  
SELECT fdhost_name, batch_count, max_thread FROM sys.dm_fts_fdhosts;  
GO  
```  
  
## <a name="see-also"></a>См. также:  
 [Динамические административные представления и функции полнотекстового поиска и семантического поиска &#40;языке Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/full-text-and-semantic-search-dynamic-management-views-functions.md)   
 [Полнотекстовый поиск](../../relational-databases/search/full-text-search.md)  
  
  
