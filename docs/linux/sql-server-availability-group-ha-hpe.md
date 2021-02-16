---
title: Развертывание группы доступности с помощью HPE Serviceguard в SQL Server на Linux
description: Использование HPE Serviceguard в качестве диспетчера кластеров для обеспечения высокой доступности с помощью группы доступности в SQL Server на Linux
ms.date: 01/15/2021
ms.prod: sql
ms.technology: linux
ms.topic: tutorial
author: amvin87
ms.author: amitkh
ms.reviewer: vanto
ms.openlocfilehash: 528d9550f79eea50db554dec11ead53039348cdb
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100051935"
---
# <a name="tutorial---setup-a-three-node-always-on-availability-group-with-hpe-serviceguard-for-linux"></a>Руководство. Настройка группы доступности Always On с тремя узлами с помощью HPE Serviceguard для Linux 

В этом руководстве содержатся сведения о настройке группы доступности Always On SQL Server с помощью решения HPE Serviceguard для Linux, запущенном на локальных виртуальных машинах.

Общие сведения о кластерах HPE Serviceguard см. [здесь](https://h20195.www2.hpe.com/v2/GetPDF.aspx/c04154488.pdf).

> [!NOTE]
> Корпорация Майкрософт поддерживает перемещение данных, группы доступности и компоненты SQL Server. Для получения поддержки, относящейся к документации по управлению кластером HPE Serviceguard и кворумом, обратитесь в HPE.

В этом руководстве рассматриваются следующие задачи:

> [!div class="checklist"]
> * Установка SQL Server на всех трех виртуальных машинах, которые будут входить в группу доступности.
> * Установка HPE Serviceguard на виртуальных машинах.
> * Создание кластера HPE Serviceguard.
> * Создание группы доступности и добавление в нее образца базы данных.
> * Развертывание рабочей нагрузки SQL Server в группе доступности с помощью диспетчера кластеров Serviceguard.
> * Выполнение автоматической отработки отказа и присоединение узла обратно к кластеру.

## <a name="prerequisites"></a>Предварительные требования

* Три виртуальные машины в локальной среде под управлением HPE Serviceguard в поддерживаемом дистрибутиве Linux.

   Пример поддерживаемого дистрибутива см. на странице [HPE Serviceguard для Linux](https://h20195.www2.hpe.com/v2/gethtml.aspx?docname=c04154488).

   Обратитесь в HPE для получения сведений о поддержке общедоступных облачных сред.

   Инструкции в этом руководстве проверены для использования с HPE Serviceguard для Linux. Пробную версию можно скачать с сайта [HPE](https://www.hpe.com/us/en/resources/servers/serviceguard-linux-trial.html).

* Файлы базы данных SQL Server в подключении логического тома (LVM) для всех трех виртуальных машин. См. [краткое руководство по началу работы с Serviceguard Linux (HPE)](https://support.hpe.com/hpesc/public/docDisplay?docId=a00107699en_us).

* Убедитесь, что на виртуальных машинах установлена среда выполнения Java OpenJDK.

   > [!NOTE]
   > Пакет SDK для Java IBM не поддерживается.

## <a name="install-sql-server"></a>Установка SQL Server

На всех трех виртуальных машинах выполните одно из приведенных ниже действий с учетом дистрибутива Linux, выбранного для этого руководства, чтобы установить SQL Server и инструменты.

### <a name="rhel"></a>RHEL

* [Установка SQL Server на Red Hat](quickstart-install-connect-red-hat.md#install)
* [Инструменты](quickstart-install-connect-red-hat.md#tools)

### <a name="sles"></a>SLES

* [Установка SQL Server в SLES](quickstart-install-connect-suse.md#install)
* [Инструменты](quickstart-install-connect-suse.md#tools)

После выполнения этого шага на всех трех виртуальных машинах, которые будут использоваться в группе доступности, должна быть установлена служба SQL Server и инструменты.

## <a name="install-hpe-serviceguard-on-the-vms"></a>Установка HPE Serviceguard на виртуальных машинах.

На этом шаге выполняется установка HPE Serviceguard для Linux на всех трех виртуальных машинах. В следующей таблице описывается роль каждого сервера в кластере.

|Число виртуальных машин | Роль HPE Serviceguard | Роль реплики группы доступности Microsoft SQL Server|
|--------------|-----------------|------------|
|1 | Узлы кластера HPE Serviceguard | Первичная реплика |
|1 или более | Узел кластера HPE Serviceguard | Вторичная реплика |
|1 | Сервер кворума HPE Serviceguard | Реплика, поддерживающая только конфигурацию |

Для установки Serviceguard воспользуйтесь методом `cminstaller`. Конкретные инструкции доступны по ссылкам ниже:

Кластер Serviceguard и сервер кворума Serviceguard

* [Установите Serviceguard для Linux на двух узлах](https://support.hpe.com/hpesc/public/docDisplay?docId=a00107699en_us#Install_serviceguard_using_cminstaller). См. раздел **Install_serviceguard_using_cminstaller**.
* [Установите сервер кворума Serviceguard на третьем узле](https://support.hpe.com/hpesc/public/docDisplay?docId=a00107699en_us#Install_QS_from_the_ISO). См. раздел **Install_QS_from_the_ISO**.

После завершения установки кластера HPE Serviceguard можно включить портал управления кластерами через TCP-порт 5522 на узле первичной реплики. Приведенные ниже действия добавляют правило к брандмауэру, чтобы разрешить порт 5522. Приведенная ниже команда предназначена для дистрибутива RHEL. Для других дистрибутивов необходимо выполнить аналогичные команды.

```console
sudo firewall-cmd --zone=public --add-port=5522/tcp --permanent

sudo firewall-cmd --reload 
```

## <a name="create-hpe-serviceguard-cluster"></a>Создание кластера HPE Serviceguard

Следуйте приведенным ниже инструкциям по созданию и настройке кластера HPE Serviceguard. На этом этапе будет также настроен сервер кворума.

1. [Настройте сервер кворума Serviceguard на третьем узле](https://support.hpe.com/hpesc/public/docDisplay?docId=a00107699en_us#Configure_QS). См. раздел **Configure_QS**.
2. [Создайте и настройте кластер Serviceguard на двух других узлах](https://support.hpe.com/hpesc/public/docDisplay?docId=a00107699en_us#Configure_and_create_cluster). См. раздел **Configure_and_create_Cluster**.

## <a name="create-the-availability-group-and-add-a-sample-database"></a>Создание группы доступности и добавление образца базы данных

На этом этапе создается группа доступности с двумя (или более) синхронными репликами и репликой, поддерживающей только конфигурацию, которая обеспечивает защиту данных, а также может обеспечить высокую доступность. Эта архитектура представлена на следующей схеме.

:::image type="content" source="media/sql-server-linux-availability-group-ha/2-configuration-only.png" alt-text="Первичная реплика синхронизирует пользовательские данные и данные конфигурации со вторичной репликой. Первичная реплика синхронизирует только данные конфигурации с репликой, поддерживающей только конфигурацию. Реплика, поддерживающая только конфигурацию, не имеет реплик пользовательских данных.":::

1. Синхронная репликация пользовательских данных на вторичную реплику. Она также включает метаданные конфигурации группы доступности.

2. Синхронная репликация метаданных конфигурации группы доступности. Она не включает пользовательские данные.

Дополнительные сведения см. в разделе [Две синхронные реплики и реплика, поддерживающая только конфигурацию](sql-server-linux-availability-group-ha.md).

Чтобы создать группу доступности, выполните следующие шаги.

1. [Включение групп доступности Always On и перезапуск mssql-server](#enable-always-on-availability-groups-and-restart-mssql-server) на всех виртуальных машинах, включая реплику, поддерживающую только конфигурацию.
2. [Включение сеанса событий `AlwaysOn_health` (необязательно)](#enable-an-alwayson_health-event-session---optional).
3. [Создание сертификата на основной виртуальной машине](#create-a-certificate-on-the-primary-vm).
4. [Создание сертификата на серверах-получателях](#create-the-certificate-on-secondary-servers)
5. [Создание конечных точек зеркального отображения базы данных на репликах](#create-the-database-mirroring-endpoints-on-the-replicas).
6. [Создание группы доступности](#create-availability-group).
7. [Присоединение вторичных реплик](#join-the-secondary-replicas).
8. [Добавление базы данных в группу доступности, созданную выше](#add-a-database-to-the-availability-group-created-above).

### <a name="enable-always-on-availability-groups-and-restart-mssql-server"></a>Включение групп доступности AlwaysOn и перезапуск mssql-server

Включите функцию Always On на всех узлах, где размещается экземпляр SQL Server. Затем перезапустите mssql-server. На всех трех узлах выполните следующий скрипт:

```console
sudo /opt/mssql/bin/mssql-conf
set hadr.hadrenabled 1 sudo systemctl restart mssql-serve
```

### <a name="enable-an-alwayson_health-event-session---optional"></a>Включение сеанса событий `AlwaysOn_health` (необязательно)

При необходимости включите расширенные события групп доступности Always On, что может помочь в устранении их неполадок. На каждом экземпляре SQL Server выполните следующую команду:

```tsql
ALTER EVENT SESSION AlwaysOn_health ON SERVER WITH (STARTUP_STATE=ON);
GO
```

### <a name="create-a-certificate-on-the-primary-vm"></a>Создание сертификата на основной виртуальной машине

Следующий сценарий Transact-SQL создает главный ключ и сертификат. Затем он создает резервную копию сертификата и защищает файл закрытым ключом. Обновите сценарий, задав надежные пароли. Подключитесь к основному экземпляру SQL Server и запустите следующий скрипт Transact-SQL:

```tsql
CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<Master_Key_Password';

CREATE CERTIFICATE dbm_certificate WITH SUBJECT = 'dbm';

BACKUP CERTIFICATE dbm_certificate TO FILE = '/var/opt/mssql/data/dbm_certificate.cer'
WITH PRIVATE KEY 
    ( FILE = '/var/opt/mssql/data/dbm_certificate.pvk',
      ENCRYPTION BY PASSWORD = '<Private_Key_Password>' );

```

На этом этапе первичная реплика SQL Server имеет сертификат в файле `/var/opt/mssql/data/dbm_certificate.cer` и закрытый ключ в файле `var/opt/mssql/data/dbm_certificate.pvk`. Скопируйте эти файлы в одно и то же место на всех серверах, где будут размещаться реплики доступности. Выберите пользователя mssql или предоставьте пользователю mssql разрешения на доступ к этим файлам.

Например, на исходном сервере указанная ниже команда копирует файлы на целевой компьютер. Замените значения `'node2'` именем узла, на котором работает вторичный экземпляр сервера SQL Server. Скопируйте сертификат на реплике, поддерживающей только конфигурацию, и выполните на этом узле приведенные ниже команды.

```console
cd /var/opt/mssql/data
scp dbm_certificate.* root@<node2>:/var/opt/mssql/data/
```

Теперь на вторичных виртуальных машинах, где работает вторичный экземпляр и реплика SQL Server, поддерживающая только конфигурацию, выполните приведенные ниже команды, чтобы пользователь mssql мог стать владельцем скопированного сертификата.

```console
cd /var/opt/mssql/data

chown mssql:mssql dbm_certificate.*
```

### <a name="create-the-certificate-on-secondary-servers"></a>Создание сертификата на серверах-получателях

Следующий сценарий Transact-SQL создает главный ключ и сертификат из резервной копии, созданной в первичной реплике SQL Server. Обновите сценарий, задав надежные пароли. Для расшифровки используется тот же пароль, что и при создании PVK-файла в предыдущем шаге. Чтобы создать сертификат, выполните следующий скрипт на всех серверах-получателях, кроме реплики, поддерживающей только конфигурацию:

```tsql
CREATE MASTER KEY ENCRYPTION BY PASSWORD =
'<Master_Key_Password>';

CREATE CERTIFICATE dbm_certificate FROM FILE =
'/var/opt/mssql/data/dbm_certificate.cer'
WITH PRIVATE KEY ( FILE = '/var/opt/mssql/data/dbm_certificate.pvk',
DECRYPTION BY PASSWORD = '<Private_Key_Password>' );
```

### <a name="create-the-database-mirroring-endpoints-on-the-replicas"></a>Создание конечных точек зеркального отображения базы данных на репликах

Чтобы создать конечные точки зеркального отображения базы данных, выполните следующие команды на первичной и вторичной репликах.

```tsql
CREATE ENDPOINT [hadr_endpoint] AS TCP (LISTENER_PORT = 5022)
    FOR DATABASE_MIRRORING 
        (
        ROLE = WITNESS,
        AUTHENTICATION = CERTIFICATE dbm_certificate,
        ENCRYPTION = REQUIRED ALGORITHM AES
        );

ALTER ENDPOINT [hadr_endpoint] STATE = STARTED;
```

> [!NOTE]
> 5022 — этот стандартный порт, используемый для конечной точки зеркального отображения базы данных, но его можно изменить на любой доступный порт.

На реплике, поддерживающей только конфигурацию, создайте конечную точку зеркального отображения базы данных с помощью приведенной ниже команды. Обратите внимание, что для роли здесь задано значение `WITNESS`, которое требуется для реплики, поддерживающей только конфигурацию.

```tsql
CREATE ENDPOINT [hadr_endpoint] AS TCP (LISTENER_PORT = 5022)
    FOR DATABASE_MIRRORING (
        ROLE = WITNESS,
        AUTHENTICATION = CERTIFICATE dbm_certificate,
        ENCRYPTION = REQUIRED ALGORITHM AES
        );

ALTER ENDPOINT [hadr_endpoint] STATE = STARTED;
```

### <a name="create-availability-group"></a>Создание группы доступности

На экземпляре первичной реплики выполните приведенные ниже команды. Они используются для создания группы доступности с именем **ag1**, которая имеет **External** `cluster_type` и предоставляет группе доступности разрешение на создание базы данных.

Перед выполнением следующих скриптов замените заполнители `<node1>`, `<node2>` и `<node3>` (для реплики, поддерживающей только конфигурацию) именами виртуальных машин, созданных на предыдущих шагах.

```tsql
CREATE AVAILABILITY GROUP [ag1]
    WITH (CLUSTER_TYPE = EXTERNAL)
    FOR REPLICA ON
    N'<node1>' WITH (
        ENDPOINT_URL = N'tcp://<node1>:<5022>',
        AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,
        FAILOVER_MODE = EXTERNAL,
        SEEDING_MODE = AUTOMATIC
        ),

    N'<node2>' WITH (
        ENDPOINT_URL = N'tcp://<node2>:\<5022>',
        AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,
        FAILOVER_MODE = EXTERNAL,
        SEEDING_MODE = AUTOMATIC
        ),
    
    N'<node3>' WITH (
        ENDPOINT_URL = N'tcp://<node3>:<5022>',
        AVAILABILITY_MODE = CONFIGURATION_ONLY
        );
          
ALTER AVAILABILITY GROUP [ag1] GRANT CREATE ANY DATABASE;
```

### <a name="join-the-secondary-replicas"></a>Присоединение вторичных реплик

Выполните приведенные ниже команды на всех вторичных репликах. Эти команды используются для присоединения вторичных реплик к группе доступности "ag1" с первичной репликой и предоставляют группе доступности ag1 доступ к базе данных.

```tsql
ALTER AVAILABILITY GROUP [ag1] JOIN WITH (CLUSTER_TYPE = EXTERNAL);
GO
ALTER AVAILABILITY GROUP [ag1] GRANT CREATE ANY DATABASE;
GO
```

### <a name="add-a-database-to-the-availability-group-created-above"></a>Добавление базы данных в группу доступности, созданную выше

Подключитесь к первичной реплике и выполните следующие команды T-SQL, чтобы выполнить следующие задачи.

1. Создание примера базы данных с именем **DB1**, которая будет добавлена в группу доступности.
2. Переключение базы данных на модель полного восстановления. Все базы данных в группе доступности должны использовать модель полного восстановления.
3. Архивируйте базу данных. Перед добавлением в группу доступности базе данных требуется хотя бы одна полная резервная копия.

```tsql
CREATE DATABASE [db1]; -- creates a database named db1
GO
ALTER DATABASE [db1] SET RECOVERY FULL; -- set the database in full recovery mode
GO
BACKUP DATABASE [db1] -- backs up the database to disk TO DISK = N'/var/opt/mssql/data/db1.bak';
GO
ALTER AVAILABILITY GROUP [ag1] ADD DATABASE [db1]; -- adds the database db1 to the AG
GO
```

После успешного выполнения предыдущих шагов вы увидите, что создана группа доступности **ag1**, и три виртуальные машины добавлены в качестве реплики с одной первичной репликой, одной вторичной репликой и одной репликой, поддерживающей только конфигурацию. **ag1** содержит одну базу данных.

## <a name="deploy-the-sql-server-availability-group-workload-hpe-cluster-manager"></a>Развертывание рабочей нагрузки группы доступности SQL Server (диспетчер кластеров HPE)

В HPE Serviceguard разверните рабочую нагрузку SQL Server в группе доступности с помощью пользовательского интерфейса диспетчера кластеров Serviceguard.
   
Разверните рабочую нагрузку группы доступности и активируйте высокий уровень доступности (HA), аварийное восстановление (DR) через кластер Serviceguard, используя [графический пользовательский интерфейс диспетчера Serviceguard](https://support.hpe.com/hpesc/public/docDisplay?docId=a00107699en_us#Protect_your_alwayson_availability_group). См. раздел **Защита Microsoft SQL Server на Linux для групп доступности Always On**.

## <a name="perform-automatic-failover-and-join-the-node-back-to-cluster"></a>Выполнение автоматической отработки отказа и присоединение узла обратно к кластеру

Для выполнения теста автоматической отработки отказа можно вывести из строя первичную реплику (отключить питание). В результате основной узел будет недоступен. Ожидаемое поведение:

1. Диспетчер кластеров повышает уровень одной из вторичных реплик в группе доступности до первичной.
2. Нерабочая первичная реплика автоматически присоединяет кластер после резервного копирования. Диспетчер кластеров повышает ее уровень до вторичной реплики.

Сведения о HPE Serviceguard см. в разделе [**Тестирования настройки для обеспечения готовности к отработке отказа**](https://support.hpe.com/hpesc/public/docDisplay?docId=a00107699en_us#Test_the_setup_preparedness)

## <a name="next-steps"></a>Дальнейшие действия

Узнайте больше о [группах доступности Always On на Linux](sql-server-linux-availability-group-overview.md).
