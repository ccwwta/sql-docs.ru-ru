---
title: sys.fn_PageResCracker (Transact-SQL) | Документация Майкрософт
description: Сведения о системной функции sys.fn_PageResCracker. См. примеры и Просмотр дополнительных доступных ресурсов.
ms.custom: ''
ms.date: 09/18/2018
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- fn_PageResCracker
- sys.fn_PageResCracker_TSQL
- fn_PageResCracker_TSQL
- sys.fn_PageResCracker
- sys.dm_db_page_info
dev_langs:
- TSQL
helpviewer_keywords:
- fn_PageResCracker function
- page_resource
- sys.fn_PageResCracker function
- sys.dm_db_page_info
- page info
author: bluefooted
ms.author: pamela
manager: amitban
ms.openlocfilehash: 49e8472353f19bcca00e68969579d4cbf6f0b538
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100064829"
---
# <a name="sysfn_pagerescracker-transact-sql"></a>sys.fn_PageResCracker (Transact-SQL)
[!INCLUDE[SQL Server 2019](../../includes/applies-to-version/sqlserver2019.md)]

Возвращает `db_id` , `file_id` и `page_id` для заданного `page_resource` значения. 
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
```  
sys.fn_PageResCracker ( page_resource )  
```  
  
## <a name="arguments"></a>Аргументы  
*page_resource*    
Является 8-байтовым шестнадцатеричным форматом ресурса страницы базы данных.
  
## <a name="tables-returned"></a>Возвращаемые таблицы  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|db_id|**int**|Идентификатор базы данных|  
|file_id|**int**|Идентификатор файла|  
|page_id|**int**|Идентификатор страницы|  
  
## <a name="remarks"></a>Remarks  
`sys.fn_PageResCracker` используется для преобразования 8-байтового шестнадцатеричного представления страницы базы данных в набор строк, содержащий идентификатор базы данных, идентификатор файла и идентификатор страницы.   

Допустимый ресурс страницы можно получить из `page_resource` столбца sys.dm_exec_requests &#40;динамическое административное представление [TRANSACT-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql.md) или [sys.sysобрабатывает &#40;системное представление&#41;Transact-SQL ](../../relational-databases/system-compatibility-views/sys-sysprocesses-transact-sql.md) . Если используется недопустимый ресурс страницы, возвращается значение NULL.  
Основное использование `sys.fn_PageResCracker` функции — упростить соединение между этими представлениями и sys.dm_db_page_info &#40;функцию динамического управления [TRANSACT-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-db-page-info-transact-sql.md) , чтобы получить сведения о странице, например объект, к которому она принадлежит.
  
## <a name="permissions"></a>Разрешения  
Пользователю требуется `VIEW SERVER STATE` разрешение на сервере.  
  
## <a name="examples"></a>Примеры  
`sys.fn_PageResCracker`Функцию можно использовать совместно с [sys.dm_db_page_info &#40;TRANSACT-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-db-page-info-transact-sql.md) для устранения неполадок, связанных с страницами, и блокировки в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  Следующий сценарий является примером того, как можно использовать эти функции для сбора сведений о странице базы данных для всех активных запросов, ожидающих некоторого типа ресурса страницы. 
  
```sql  
SELECT page_info.* 
FROM sys.dm_exec_requests AS d  
CROSS APPLY sys.fn_PageResCracker (d.page_resource) AS r  
CROSS APPLY sys.dm_db_page_info(r.db_id, r.file_id, r.page_id, 1) AS page_info
```  
  
## <a name="see-also"></a>См. также:  
 [sys.dm_db_page_info &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-db-page-info-transact-sql.md)  
 [sys.sysные процессы &#40;&#41;Transact-SQL ](../../relational-databases/system-compatibility-views/sys-sysprocesses-transact-sql.md)   
 [sys.dm_exec_requests (Transact-SQL)](../../relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql.md)  
  
  
