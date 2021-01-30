---
description: sysmail_help_configure_sp (Transact-SQL)
title: sysmail_help_configure_sp (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sysmail_help_configure_sp
- sysmail_help_configure_sp_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysmail_help_configure_sp
ms.assetid: e598d4c8-3041-4965-b046-dce3a8e3d3e0
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 21ce11d37659561e172c11fb7b5a899193141166
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99181973"
---
# <a name="sysmail_help_configure_sp-transact-sql"></a>sysmail_help_configure_sp (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Отображает настройки конфигурации компонента Database Mail.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sysmail_help_configure_sp  [ [ @parameter_name = ] 'parameter_name' ]  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @parameter_name = ] 'parameter_name'` Имя параметра конфигурации для извлечения. При указании значения параметра конфигурации возвращается в параметре OUTPUT **\@ parameter_value** . Если **\@ parameter_name** не указано, эта хранимая процедура возвращает результирующий набор, содержащий все параметры конфигурации Database Mail в экземпляре.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (сбой)  
  
## <a name="result-sets"></a>Результирующие наборы  
 Если **\@ parameter_name** не указано, возвращает результирующий набор со следующими столбцами.  
  
| Имя столбца | Тип данных | Описание |
| ----------- | --------- | ----------- |
|**paramName**|**nvarchar(256)**|Имя параметра конфигурации.|  
|**paramvalue**|**nvarchar(256)**|Значение параметра конфигурации.|  
|**description**|**nvarchar(256)**|Описание параметра конфигурации.|  
  
## <a name="remarks"></a>Замечания  
 Хранимая процедура **sysmail_help_configure_sp** перечисляет текущие параметры конфигурации Database Mail для экземпляра.  
  
 Если указан **\@ parameter_name** , но для **\@ parameter_value** не задан выходной параметр, эта хранимая процедура не создает выходных данных.  
  
 Хранимая процедура **sysmail_help_configure_sp** находится в базе данных **msdb** и принадлежит схеме **dbo** . Процедура должна быть вызвана с именем, сопоставленным с тремя частями, если текущей базой данных не является **msdb**.  
  
## <a name="permissions"></a>Разрешения  
 По умолчанию разрешения EXECUTE для этой процедуры имеют члены предопределенной роли сервера **sysadmin** .  
  
## <a name="examples"></a>Примеры  
 В следующем примере процедура отображает список параметров конфигурации компонента Database Mail для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
```  
EXECUTE msdb.dbo.sysmail_help_configure_sp ;  
```  
  
 Далее приведен образец результирующего набора, отредактированного по длине строк:  
  
```  
paramname                       paramvalue      description  
------------------------------- --------------- -----------------------------------------------------------------------------  
AccountRetryAttempts            1               Number of retry attempts for a mail server  
AccountRetryDelay               5000            Delay between each retry attempt to mail server  
DatabaseMailExeMinimumLifeTime  600             Minimum process lifetime in seconds  
DefaultAttachmentEncoding       MIME            Default attachment encoding  
LoggingLevel                    2               Database Mail logging level: normal - 1, extended - 2 (default), verbose - 3  
MaxFileSize                     1000000         Default maximum file size  
ProhibitedExtensions            exe,dll,vbs,js  Extensions not allowed in outgoing mails  
  
```  
  
## <a name="see-also"></a>См. также:  
 [Database Mail](../../relational-databases/database-mail/database-mail.md)   
 [Database Mail хранимых процедур &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/database-mail-stored-procedures-transact-sql.md)  
  
  
