---
description: cursor (Transact-SQL)
title: cursor (Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 07/23/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- cursor data type
ms.assetid: fbea16ef-f2cc-4734-9149-ec2598fd3cca
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 858a6200e1e1d74f5610d61e85a2b5dde3248e61
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99205484"
---
# <a name="cursor-transact-sql"></a>cursor (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

Тип данных для переменных или выходных параметров хранимых процедур, которые содержат ссылку на курсор.
  
## <a name="remarks"></a>Комментарии  
Операции, которые могут выполняться с переменными и параметрами, имеющими тип данных **cursor**:
-   Инструкции DECLARE *\@local_variable* и SET *\@local_variable*.  
-   Инструкции над курсором OPEN, FETCH, CLOSE и DEALLOCATE.  
-   Выходные параметры хранимой процедуры.  
-   Функция CURSOR_STATUS.  
-   Системные хранимые процедуры **sp_cursor_list**, **sp_describe_cursor**, **sp_describe_cursor_tables** и **sp_describe_cursor_columns**.  
  
Выходной столбец **cursor_name** хранимых процедур **sp_cursor_list** и **sp_describe_cursor** возвращает имя переменной курсора.
  
Любая переменная, созданная с типом данных **cursor**, может принимать значение NULL.
  
Тип данных **cursor** не может использоваться для столбца в операторе CREATE TABLE.
  
## <a name="see-also"></a>См. также раздел
[Функции CAST и CONVERT (Transact-SQL)](../../t-sql/functions/cast-and-convert-transact-sql.md)  
[CURSOR_STATUS (Transact-SQL)](../../t-sql/functions/cursor-status-transact-sql.md)  
[Преобразование типов данных (ядро СУБД)](../../t-sql/data-types/data-type-conversion-database-engine.md)  
[Типы данных (Transact-SQL)](../../t-sql/data-types/data-types-transact-sql.md)  
[DECLARE CURSOR (Transact-SQL)](../../t-sql/language-elements/declare-cursor-transact-sql.md)  
[DECLARE @local_variable &#40;Transact-SQL&#41;](../../t-sql/language-elements/declare-local-variable-transact-sql.md)  
[SET @local_variable &#40;Transact-SQL&#41;](../../t-sql/language-elements/set-local-variable-transact-sql.md)
  
  
