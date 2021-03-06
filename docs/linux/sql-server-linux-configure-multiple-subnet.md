---
title: Настройка групп доступности и экземпляров отказоустойчивого кластера с несколькими подсетями (Linux)
description: Узнайте, как настроить группы доступности Always On и экземпляры отказоустойчивого кластера в конфигурации с несколькими подсетями для SQL Server на Linux.
ms.custom: seo-lt-2019
author: liweiSecurity
ms.author: liweiyin
ms.reviewer: VanMSFT
ms.date: 07/28/2020
ms.topic: conceptual
ms.prod: sql
ms.technology: linux
ms.openlocfilehash: 5abe1d99f753e0f41ca74a0864079293800dc1df
ms.sourcegitcommit: 99f61724de5edf6640efd99916d464172eb23f92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87362997"
---
# <a name="configure-multiple-subnet-always-on-availability-groups-and-failover-cluster-instances"></a>Настройка групп доступности Always On и экземпляров отказоустойчивого кластера для конфигураций с несколькими подсетями

[!INCLUDE [SQL Server - Linux](../includes/applies-to-version/sql-linux.md)]

Если группа доступности Always On или экземпляр отказоустойчивого кластера охватывают несколько сайтов, каждый сайт обычно использует собственную сеть. Зачастую это означает, что каждый сайт использует собственную систему IP-адресации. Например, адреса сайта А начинаются с 192.168.1.*x*, а сайта Б с 192.168.2.*x*, где часть *x* IP-адреса является уникальной для конкретного сервера. Чтобы обеспечить возможность взаимодействия между серверами, необходимо реализовать определенный механизм маршрутизации на уровне сети. В таком сценарии возможны два подхода: настройка сети, связывающей две разных подсети (виртуальная локальная сеть) или настройка маршрутизации между подсетями.

## <a name="vlan-based-solution"></a>Решение на основе виртуальной локальной сети
 
**Предварительное требование**: Для решения на основе виртуальной локальной сети каждый сервер, участвующий в группе доступности Always On или экземпляре отказоустойчивого кластера, должен быть оснащен двумя сетевыми адаптерами, чтобы обеспечить необходимый уровень доступности (сетевой адаптер с двумя портами будет выступать в качестве единой точки отказа на физическом сервере).Такой подход позволяет назначать IP-адреса в собственной сети сервера, а также в виртуальной локальной сети. Это требование устанавливается в дополнение к любым другим, таким как интерфейс iSCSI, который также использует собственную сеть.

Создание IP-адресов для группы доступности Always On или экземпляра отказоустойчивого кластера осуществляется в виртуальной локальной сети. В следующем примере виртуальная локальная сеть содержит подсеть 192.168.3.*x*, поэтому для группы доступности Always On или экземпляра отказоустойчивого кластера создается IP-адрес 192.168.3.104. Поскольку группе доступности Always On или экземпляру отказоустойчивого кластера назначается один IP-адрес, дополнительная настройка не требуется.

![Настройка нескольких подсетей 01](./media/sql-server-linux-configure-multiple-subnet/image1.png)

## <a name="configuration-with-pacemaker"></a>Настройка с использованием Pacemaker

В среде Windows отказоустойчивый кластер Windows Server (WSFC) изначально поддерживает несколько подсетей и обрабатывает множественные IP-адреса посредством зависимости OR от IP-адреса. В среде Linux зависимость OR отсутствует, однако можно обеспечить собственную поддержку работы в нескольких подсетях с использованием Pacemaker, как показано ниже. Обратите внимание, что сделать это путем изменения ресурса с помощью обычной командной строки Pacemaker нельзя. Вам необходимо изменить базу информации о кластере. База информации о кластере представляет собой XML-файл с конфигурацией Pacemaker.

![Настройка нескольких подсетей 02](./media/sql-server-linux-configure-multiple-subnet/image2.png)

### <a name="update-the-cib"></a>Обновление базы информации о кластере

1. Экспорт базы информации о кластере.

    **Red Hat Enterprise Linux (RHEL) и Ubuntu**

    ```bash
    sudo pcs cluster cib <filename>
    ```

    **SUSE Linux Enterprise Server (SLES)**

    ```bash
    sudo cibadmin -Q > <filename>
    ```

    Здесь *filename* — это имя, присваиваемое базе информации о кластере.

2. Измените созданный файл. Найдите раздел `<resources>`. Обратите внимание на различные группы ресурсов, которые были созданы для группы доступности Always On или экземпляра отказоустойчивого кластера. Найдите ресурс, связанный с IP-адресом. Добавьте раздел `<instance attributes>` со сведениями о втором IP-адресе непосредственно перед существующим или после него, но до раздела `<operations>`. Синтаксис будет выглядеть примерно так:

    ```xml
    <instance attributes id="<NameForAttribute>">
        <nvpair id="<NameForIP>" name="ip" value="<IPAddress>"/>
    </instance attributes>
    ```
    
    где *NameForAttribute* — это уникальное имя атрибута, *NameForIP* — это имя, связанное с IP-адресом, а *IPAddress* — это IP-адрес второй подсети.
    
    Ниже приводится пример.
    
    ```xml
    <instance attributes id="virtualip-instance_attributes">
        <nvpair id="virtualip-instance_attributes-ip" name="ip" value="192.168.1.102"/>
    </instance attributes>
    ```
    
    По умолчанию в экспортированном XML-файле базы информации о кластере есть только один <instance/>. Предположим, у вас есть две подсети и вам нужны две записи <instance/>.
    Ниже приведен пример записей для двух подсетей
    
    ```xml
    <instance attributes id="virtualip-instance_attributes1">
        <rule id="Subnet1-IP" score="INFINITY" boolean-op="or">
            <expression id="Subnet1-Node1" attribute="#uname" operation="eq" value="Node1" />
            <expression id="Subnet1-Node2" attribute="#uname" operation="eq" value="Node2" />
        </rule>
        <nvpair id="IP-In-Subnet1" name="ip" value="192.168.1.102"/>
    </instance attributes>
    <instance attributes id="virtualip-instance_attributes2">
        <rule id="Subnet2-IP" score="INFINITY">
            <expression id="Subnet2-Node1" attribute="#uname" operation="eq" value="Node3" />
        </rule>
        <nvpair id="IP-In-Subnet2" name="ip" value="192.168.2.102"/>
    </instance attributes>
    ```
   
   Выражение boolean-op="or" используется, если у подсети более одного сервера.


3. Импорт измененной базы информации о кластере и изменение настройки Pacemaker.

    **RHEL/Ubuntu**
    
    ```bash
    sudo pcs cluster cib-push <filename>
    ```

    **SLES**
    
    ```bash
    sudo cibadmin -R -x <filename>
    ```

    Здесь *filename* — это имя файла для базы информации о кластере, содержащей измененные сведения об IP-адресах.

### <a name="check-and-verify-failover"></a>Проверка изменений и отработки отказа

1. После успешного применения базы информации о кластере с обновленной конфигурацией проверьте связь с DNS-именем, которое связано с ресурсом IP-адреса в Pacemaker. Он должен отражать IP-адрес, связанный с подсетью, в которой в данный момент размещаются группа доступности Always On или экземпляр отказоустойчивого кластера.

2. Выполните отработку отказа группы доступности Always On или экземпляра отказоустойчивого кластера в другой подсети.

3. После полного подключения группы доступности Always On или экземпляра отказоустойчивого кластера проверьте связь с DNS-именем, которое связано с IP-адресом. Он должен отражать IP-адрес во второй подсети.

4. При необходимости выполните отработку отказа группы доступности Always On или экземпляра отказоустойчивого кластера в исходной подсети.

Ниже приведена запись CSS, в которой показано, как настроить базу информации о кластере для трех подсетей. Дополнительные сведения см.: [Настройка группы доступности Always On с несколькими подсетями путем изменения базы информации о кластере](https://techcommunity.microsoft.com/t5/sql-server-support/configure-multiple-subnet-alwayson-availability-groups-by/ba-p/1544838).
