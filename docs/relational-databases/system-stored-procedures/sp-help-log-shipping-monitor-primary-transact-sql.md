---
description: sp_help_log_shipping_monitor_primary (Transact-SQL)
title: sp_help_log_shipping_monitor_primary (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sp_help_log_shipping_monitor_primary
- sp_help_log_shipping_monitor_primary_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_help_log_shipping_monitor_primary
ms.assetid: d9dfcb8f-1da6-49ca-a2c8-411574915434
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 732db5c1427526a62b8103444c0ca7063442dae6
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99200080"
---
# <a name="sp_help_log_shipping_monitor_primary-transact-sql"></a>sp_help_log_shipping_monitor_primary (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Возвращает сведения, касающиеся базы данных-источника из таблиц мониторинга.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_help_log_shipping_monitor_primary  
[ @primary_server = ] 'primary_server',   
[ @primary_database = ] 'primary_database'  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @primary_server = ] 'primary_server'` Имя основного экземпляра в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] конфигурации доставки журналов. *primary_server* имеет тип **sysname** и не может иметь значение null.  
  
`[ @primary_database = ] 'primary_database'` Имя базы данных на сервере-источнике. Аргумент *primary_database* имеет тип **sysname** и не имеет значения по умолчанию.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 0 (успешное завершение) или 1 (неуспешное завершение)  
  
## <a name="result-sets"></a>Результирующие наборы  
  
|Имя столбца|Описание|  
|-----------------|-----------------|  
|**primary_id**|Идентификатор базы данных-источника в конфигурации доставки журналов.|  
|**primary_server**|Имя первичного экземпляра компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] в конфигурации доставки журнала.|  
|**primary_database**|Имя базы данных-источника в конфигурации доставки журналов.|  
|**backup_threshold**|Максимальное время ожидания (в минутах) между операциями резервного копирования перед созданием предупреждения.|  
|**threshold_alert**|Предупреждение, создаваемое при превышении порогового значения.|  
|**threshold_alert_enabled**|Определяет, включены ли пороговые предупреждения резервного копирования. 1 = включены; 0 = отключены.|  
|**last_backup_file**|Абсолютный путь последней резервной копии журнала транзакций.|  
|**last_backup_date**|Время и дата последней операции резервного копирования журнала транзакций базы данных-источника.|  
|**last_backup_date_utc**|Время и дата создания последней резервной копии журнала транзакций в базе данных-источнике, выраженные в формате UTC.|  
|**history_retention_period**|Промежуток времени в минутах, после которого записи истории доставки журнала данной базы данных-источника будут удалены.|  
  
## <a name="remarks"></a>Замечания  
 **sp_help_log_shipping_monitor_primary** должны быть запущены из базы данных **master** на сервере мониторинга.  
  
## <a name="permissions"></a>Разрешения  
 Эту процедуру могут выполнять только члены предопределенной роли сервера **sysadmin** .  
  
## <a name="see-also"></a>См. также:  
 [Сведения о доставке журналов (SQL Server)](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
