---
description: sys.dm_cryptographic_provider_keys (Transact-SQL)
title: sys.dm_cryptographic_provider_keys (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sys.dm_cryptographic_provider_keys_TSQL
- dm_cryptographic_provider_keys_TSQL
- dm_cryptographic_provider_keys
- sys.dm_cryptographic_provider_keys
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_cryptographic_provider_keys dynamic management function
ms.assetid: 5a8c1421-c56b-44b5-96e5-4f01782a0c7c
author: WilliamDAssafMSFT
ms.author: wiassaf
ms.openlocfilehash: 508240f27248cb4cc618441948c40b72c9311398
ms.sourcegitcommit: 58e7069b5b2b6367e27b49c002ca854b31b1159d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2021
ms.locfileid: "99552614"
---
# <a name="sysdm_cryptographic_provider_keys-transact-sql"></a>sys.dm_cryptographic_provider_keys (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Возвращает сведения о ключах, предоставленных поставщиком расширенного управления ключами.  

 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  

> [!IMPORTANT]
> Это динамическое административное представление в настоящее время не поддерживается соединителем расширенного управления ключами SQL Server. Группа разработчиков SQL Serverа осведомлена об этой ошибке и будет решать эту задачу в будущем.

## <a name="syntax"></a>Синтаксис  
  
```  
  
dm_cryptographic_provider_keys ( provider_id )  
```  
  
## <a name="arguments"></a>Аргументы  
 *provider_id*  
 Идентификационный номер поставщика расширенного управления ключами, без значения по умолчанию.  
  
## <a name="tables-returned"></a>Возвращаемые таблицы  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**key_id**|**int**|Идентификатор ключа на поставщике.|  
|**key_name**|**nvarchar(512)**|Имя ключа на поставщике.|  
|**key_thumbprint**|**varbinary(32)**|Отпечаток с поставщика ключа.|  
|**algorithm_id**|**int**|Идентификатор алгоритма на поставщике.|  
|**algorithm_tag**|**int**|Тег алгоритма на поставщике.|  
|**key_type**|**nchar (256)**|Тип ключа на поставщике.|  
|**key_length**|**int**|Длина ключа на поставщике.|  
  
## <a name="permissions"></a>Разрешения  
 При запросе к этому представлению выполняется проверка подлинности контекста пользователя на поставщике расширенного управления ключами и перечисление всех ключей, видимых для пользователя.  
  
 Если проверку подлинности пользователя на поставщике расширенного управления ключами выполнить не удалось, данные ключей не возвращаются.  
  
## <a name="examples"></a>Примеры  
 В следующем примере демонстрируются свойства ключа для поставщика с идентификатором `1234567`.  
  
```  
SELECT * FROM sys.dm_cryptographic_provider_keys(1234567);  
GO  
```  
  
## <a name="see-also"></a>См. также:  
 [Расширенное управление ключами &#40;EKM&#41;](../../relational-databases/security/encryption/extensible-key-management-ekm.md)  
  
  
