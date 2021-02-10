---
description: sys.dm_column_encryption_enclave (Transact-SQL)
title: sys.dm_column_encryption_enclave (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 10/11/2019
ms.prod: sql
ms.reviewer: vanto
ms.technology: system-objects
ms.topic: reference
author: jaszymas
ms.author: jaszymas
monikerRange: '>= sql-server-ver15'
ms.openlocfilehash: 69566b93843fdd7d0328a31e0bfb86be9e3fa4bb
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100062219"
---
# <a name="sysdm_column_encryption_enclave-transact-sql"></a>sys.dm_column_encryption_enclave (Transact-SQL)
[!INCLUDE [sqlserver2019-windows-only](../../includes/applies-to-version/sqlserver2019-windows-only.md)]

Возвращает счетчики производительности для безопасного анклава для Always Encrypted. Дополнительные сведения см. в статье [Always Encrypted с безопасными анклавами](../security/encryption/always-encrypted-enclaves.md).

Если анклава настроен и правильно инициализирован после последнего перезапуска [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , представление содержит ровно одну строку. Если анклава не настроен или не был правильно инициализирован, представление не возвращает никаких строк. 

|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|current_enclave_session_count|**int**|Текущее количество клиентских сеансов, использующих анклава.|  
|current_column_encryption_key_count|**int**|Число ключей шифрования столбцов, которые в настоящее время содержатся в анклава.|  
|current_memory_size_kb|**bigint**|Размер памяти анклава в КБ|  
|total_evicted_session_count|**bigint**|Общее число сеансов анклава, удаленных с момента последнего перезапуска сервера.|   
  
## <a name="permissions"></a>Разрешения  
Требуется разрешение `VIEW SERVER STATE`.   
  
## <a name="examples"></a>Примеры  
 
```sql  
SELECT * FROM sys.dm_column_encryption_enclave;  
GO  
```  
  
## <a name="see-also"></a>См. также:  
 [Настройка типа анклава для параметра конфигурации сервера Always Encrypted](../../database-engine/configure-windows/configure-column-encryption-enclave-type.md)
  
  
