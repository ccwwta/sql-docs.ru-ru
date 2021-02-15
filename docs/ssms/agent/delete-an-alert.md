---
title: Удаление предупреждения
description: Удаление предупреждения
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], deleting
- deleting alerts
- canceling alerts
- dropping alerts
- disabling alerts
- removing alerts
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.custom: seo-lt-2019
ms.date: 02/04/2021
monikerRange: = azuresqldb-mi-current || >= sql-server-2016
ms.openlocfilehash: bf4cefa3d6bcd307b80ae4f4dc0944cdb18bcdba
ms.sourcegitcommit: 0b400bb99033f4b836549cb11124a1f1630850a1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "99978792"
---
# <a name="delete-an-alert"></a>Удаление предупреждения

[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]
> В [Управляемом экземпляре Azure SQL](/azure/sql-database/sql-database-managed-instance) в настоящее время поддерживается большинство функций агента SQL Server (но не все). Подробные сведения см. в статье [Различия в T-SQL между Управляемым экземпляром SQL Azure и SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent).

В этой статье описано, как удалить предупреждения агента Microsoft SQL Server с помощью SQL Server Management Studio или Transact-SQL.

## <a name="before-you-begin"></a><a name="BeforeYouBegin"></a>Подготовка к работе

### <a name="limitations-and-restrictions"></a><a name="Restrictions"></a>Ограничения

Удаление предупреждения приводит также к удалению всех связанных с ним уведомлений.

### <a name="security"></a><a name="Security"></a>безопасность

#### <a name="permissions"></a><a name="Permissions"></a>Permissions

По умолчанию только члены предопределенной роли сервера **sysadmin** могут удалять предупреждения.  

## <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a>Использование среды SQL Server Management Studio

### <a name="to-delete-an-alert"></a>Удаление предупреждения

1. В **обозревателе объектов** щелкните значок "плюс", чтобы развернуть сервер, содержащий предупреждение агента SQL Server, которое необходимо удалить.

2. Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.

3. Чтобы развернуть папку **Предупреждения**, щелкните значок "плюс".

4. Щелкните правой кнопкой мыши предупреждение, которое необходимо удалить, и выберите пункт **Удалить**.

5. В диалоговом окне **Удаление объекта** убедитесь в том, что выбрано верное предупреждение, и нажмите кнопку **ОК**.

## <a name="using-transact-sql"></a><a name="TsqlProcedure"></a>Использование Transact-SQL

### <a name="to-delete-an-alert"></a>Удаление предупреждения

1. В **обозревателе объектов** подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde_md.md)].

2. На стандартной панели выберите пункт **Создать запрос**.  

3. Скопируйте приведенный ниже пример в окно запроса и нажмите кнопку **Выполнить**.

    ```
    -- deletes the SQL Server Agent alert called 'Test Alert.'
    USE msdb ;
    GO
  
    EXEC dbo.sp_delete_alert
       @name = N'Test Alert' ;
    GO
    ```

Дополнительные сведения см. в разделе [sp_delete_alert (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-delete-alert-transact-sql.md).
