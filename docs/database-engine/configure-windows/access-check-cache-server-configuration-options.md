---
title: Параметры конфигурации сервера "access check cache" | Документы Майкрософт
description: Описание кеша результатов проверки доступа и параметров, которые управляют его поведением. Сведения об изменении этих параметров в SQL Server.
ms.custom: ''
ms.date: 03/02/2017
ms.prod: sql
ms.prod_service: high-availability
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- access check cache option
- access check cache bucket count
- access check cache quota
ms.assetid: 0a992ea8-3ec6-4a4d-97b5-460ae7326247
author: markingmyname
ms.author: maghan
ms.openlocfilehash: dc1ff18d464c03d1eb5e96834f4d753bfead5559
ms.sourcegitcommit: b1cec968b919cfd6f4a438024bfdad00cf8e7080
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2021
ms.locfileid: "99233976"
---
# <a name="access-check-cache-server-configuration-options"></a>Параметры конфигурации сервера «access check cache»
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

При доступе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]к объектам базы данных проверка доступа кэшируется во внутренней структуре, которую называют **кэшем результатов проверки доступа**. 
  
Параметр **доступ к счетчику контейнеров проверки кэша** контролирует количество сегментов хэша, используемых для кэша результатов проверки доступа. 

Параметр **доступ к квоте кэша проверки** контролирует количество записей, хранящихся в кэше результатов проверки доступа. При достижении максимального количества записей самые старые записи удаляются из кэша результатов проверки доступа.
  
Значение по умолчанию 0 указывает на то, что этими параметрами управляет [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Начиная с [!INCLUDE[sssql16-md](../../includes/sssql16-md.md)], значения по умолчанию преобразуются в следующие внутренние конфигурации:
-   Для счетчика контейнеров кэша проверки доступа значение 0 устанавливает значение по умолчанию, которое составляет 256 сегментов.
-   Для квоты кэша проверки доступа значение 0 устанавливает значение по умолчанию, которое составляет 1024 записи.

В редких случаях можно добиться увеличения производительности, изменив эти параметры. Например, если используется слишком много памяти, возможно, придется уменьшить размер кэша результатов проверки доступа. Также может потребоваться увеличить размер кэша результатов проверки доступа, если при пересчете разрешений возникнет высокая загрузка ЦП.
 
> [!IMPORTANT]
> Майкрософт рекомендует изменять эти параметры только под руководством службы поддержки пользователей Майкрософт. Если значения "счетчике контейнеров кэша проверки доступа" или "квоты кэша проверки доступа" необходимо изменить, используйте соотношение 1:4. Например, если вы меняете значение "счетчика контейнеров кэша проверки доступа" на 512, значение "квоты кэша проверки доступа" нужно изменить на 2048. 
  
## <a name="see-also"></a>См. также:  
 [Параметры конфигурации сервера (SQL Server)](../../database-engine/configure-windows/server-configuration-options-sql-server.md)   
 [sp_configure (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)  
  
  
