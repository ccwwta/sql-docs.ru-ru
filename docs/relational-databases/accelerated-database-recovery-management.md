---
description: Управление ускоренным восстановлением баз данных
title: Управление ускоренным восстановлением базы данных | Документация Майкрософт
ms.date: 02/02/2021
ms.prod: sql
ms.prod_service: backup-restore
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- accelerated database recovery [SQL Server], recovery-only
- database recovery [SQL Server]
author: mashamsft
ms.author: mathoma
ms.reviewer: kfarlee
monikerRange: '>=sql-server-ver15'
ms.openlocfilehash: 28ab5d23e4a2dc3168a9682424b3cb11a8e0b70e
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100062214"
---
# <a name="manage-accelerated-database-recovery"></a>Управление ускоренным восстановлением баз данных

[!INCLUDE[sqlserver](../includes/applies-to-version/sqlserver2019.md)]

## <a name="enabling-and-controlling-adr"></a>Включение и управление ADR

Функция ADR в [!INCLUDE[sql-server-2019](../includes/sssql19-md.md)] по умолчанию отключена. Ею можно управлять с помощью синтаксиса DDL:
```sql
ALTER DATABASE [DB] SET ACCELERATED_DATABASE_RECOVERY = {ON | OFF}
[(PERSISTENT_VERSION_STORE_FILEGROUP = { filegroup name }) ];

```

Используя этот синтаксис, можно включать или отключать функцию, а также назначать определенную файловую группу для данных *постоянного хранилища версий* (PVS). Если файловая группа не указана, PVS сохраняется в файловой группе PRIMARY.

## <a name="managing-the-persistent-version-store-filegroup"></a>Управление файловой группой постоянного хранилища версий
Функция ADR основана на управлении версиями. Различные версии элементов данных хранятся в PVS.
Существуют рекомендации по размещению PVS и управлению размером данных в PVS.

### <a name="to-enable-adr-without-specifying-a-filegroup"></a>Включение ADR без указания файловой группы

```sql
ALTER DATABASE [MyDatabase] SET ACCELERATED_DATABASE_RECOVERY = ON;
GO
```

Если файловая группа PVS не указана, данные PVS хранятся в файловой группе `PRIMARY`.

### <a name="to-enable-adr-and-specify-that-the-pvs-should-be-stored-in-the-versionstorefg-filegroup"></a>Включение ADR и настройка хранения PVS в файловой группе [VersionStoreFG]

Перед запуском этого скрипта создайте файловую группу.

```sql
ALTER DATABASE [MyDatabase] SET ACCELERATED_DATABASE_RECOVERY = ON
(PERSISTENT_VERSION_STORE_FILEGROUP = [VersionStoreFG])
```

### <a name="to-disable-the-adr-feature"></a>Отключение функции ADR

```sql
ALTER DATABASE [MyDatabase] SET ACCELERATED_DATABASE_RECOVERY = OFF;
GO
```

Даже после отключения функции ADR в постоянном хранилище версий будут храниться версии, которые по-прежнему требуются системе для логической отмены.

### <a name="change-the-location-of-the-pvs-to-a-different-filegroup"></a>Перемещение PVS в другую файловую группу

PVS может потребоваться переместить в другую файловую группу по тем или иным причинам. Например, для PVS может потребоваться больше места или более быстрое хранилище.

Перемещение PVS выполняется в три этапа.

1. Отключите функцию ADR.

   ```sql
   ALTER DATABASE [MyDatabase] SET ACCELERATED_DATABASE_RECOVERY = OFF;
   GO
   ```

2. Подождите, пока все версии, хранящиеся в PVS, можно будет освободить.

   Чтобы можно было включить ADR с новым расположением постоянного хранилища версий, сначала необходимо убедиться в том, что все сведения о версиях были удалены из предыдущего расположения PVS. Чтобы произвести очистку принудительно, выполните следующую команду:

   ```sql
   EXEC sys.sp_persistent_version_cleanup [database name]
   ```

   Хранимая процедура `sys.sp_persistent_version_cleanup` является синхронной, то есть она не будет завершена до тех пор, пока все сведения о версиях не будут удалены из текущего хранилища PVS.  После завершения ее выполнения можно проверить, действительно ли сведения о версиях были удалены, запросив динамическое административное представление `sys.dm_persistent_version_store_stats` и проверив значение `persistent_version_store_size_kb`.

   ```sql
   SELECT DB_Name(database_id), persistent_version_store_size_kb 
   FROM sys.dm_tran_persistent_version_store_stats where database_id = [MyDatabaseID]
   ```

   Если значение persistent_version_store_size_kb равно 0, можно повторно включить функцию ADR, настроив размещение PVS в новой файловой группе.

1. Включение ADR с указанием нового расположения PVS

   ```sql
   ALTER DATABASE [MyDatabase] SET ACCELERATED_DATABASE_RECOVERY = ON
   (PERSISTENT_VERSION_STORE_FILEGROUP = [VersionStoreFG])
   ```

## <a name="troubleshooting"></a>Устранение неполадок

> [!NOTE]
> Этот раздел относится также к базе данных Azure SQL.

Выполните запрос к `sys.dm_tran_persistent_version_store_stats`, чтобы проверить размер PVS.

Проверьте размер `% of DB`. Также обратите внимание на отличие от обычного размера.

Хранилище PVS считается большим, если его размер значительно больше базового уровня или близок к 50 % от размера базы данных. 

1. Получите `oldest_active_transaction_id` и проверьте, была ли эта транзакция активна в течение длительного времени, выполнив запрос к `sys.dm_tran_database_transactions` по идентификатору транзакции.

   Активные транзакции препятствуют очистке PVS.

2. Если база данных входит в группу доступности, проверьте значение `secondary_low_water_mark`. Оно аналогично значению `low_water_mark_for_ghosts`, сообщаемому `sys.dm_hadr_database_replica_states`. Выполните запрос к `sys.dm_hadr_database_replica_states`, чтобы определить, блокирует ли одна из реплик это значение, так как это также предотвратит очистку PVS.
3. Проверьте значение `min_transaction_timestamp` (или `online_index_min_transaction_timestamp`, если блокировка производится активным хранилищем PVS) и в соответствии с результатом проверьте значение `sys.dm_tran_active_snapshot_database_transactions` для столбца `transaction_sequence_num`, чтобы определить сеанс, в котором содержится старая транзакция моментального снимка, блокирующая очистку PVS.
4. Если ни одна из указанных выше проверок не дала результата, значит, очистка блокируется аварийно завершенными транзакциями. Проверьте последнее время `aborted_version_cleaner_last_start_time` и `aborted_version_cleaner_last_end_time`, чтобы узнать, завершилась ли очистка аварийно завершенных транзакций. После очистки аварийно завершенных транзакций значение `oldest_aborted_transaction_id` должно быть больше.
5. Если аварийно завершенная транзакция не была успешно выполнена недавно, проверьте наличие сообщений о проблемах `VersionCleaner` в журнале ошибок.

Используйте следующий пример запроса в качестве средства устранения неполадок:

```sql
SELECT pvss.persistent_version_store_size_kb / 1024. / 1024 AS persistent_version_store_size_gb,
       pvss.online_index_version_store_size_kb / 1024. / 1024 AS online_index_version_store_size_gb,
       pvss.current_aborted_transaction_count,
       pvss.aborted_version_cleaner_start_time,
       pvss.aborted_version_cleaner_end_time,
       dt.database_transaction_begin_time AS oldest_transaction_begin_time,
       asdt.session_id AS active_transaction_session_id,
       asdt.elapsed_time_seconds AS active_transaction_elapsed_time_seconds
FROM sys.dm_tran_persistent_version_store_stats AS pvss
LEFT JOIN sys.dm_tran_database_transactions AS dt
ON pvss.oldest_active_transaction_id = dt.transaction_id
   AND
   pvss.database_id = dt.database_id
LEFT JOIN sys.dm_tran_active_snapshot_database_transactions AS asdt
ON pvss.min_transaction_timestamp = asdt.transaction_sequence_num
   OR
   pvss.online_index_min_transaction_timestamp = asdt.transaction_sequence_num
WHERE pvss.database_id = DB_ID();
```
