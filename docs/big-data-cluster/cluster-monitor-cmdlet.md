---
title: Мониторинг кластера с помощью azdata и kubectl
titleSuffix: SQL Server Big Data Clusters
description: Мониторинг приложений с помощью azdata и kubectl в кластере больших данных SQL Server 2019.
author: cloudmelon
ms.author: melqin
ms.reviewer: mikeray
ms.metadata: seo-lt-2019
ms.date: 09/22/2020
ms.topic: conceptual
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: c82aad4ae4fb808f9e657a0c5cbd1a6172c45c53
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100039450"
---
# <a name="monitor-cluster-with-azdata-and-kubectl"></a>Мониторинг кластера с помощью azdata и kubectl

## <a name="use-azdata"></a>Использование azdata

Для просмотра обеих конечных точек и состояния кластера также можно использовать команды [azdata](../azdata/install/deploy-install-azdata.md).

### <a name="service-endpoints"></a>Конечные точки служб

1. Войдите в кластер больших данных с помощью [azdata login](../azdata/reference/reference-azdata.md). Задайте для параметра **--controller-endpoint** значение внешнего IP-адреса конечной точки контроллера.

   ```bash
   azdata login --endpoint https://<ip-address-of-controller-svc-external>:30080 --username <user-name>
   ```

1. Укажите имя пользователя и пароль, настроенные для контроллера (AZDATA_USERNAME и AZDATA_PASSWORD) во время развертывания.

   Для проверки подлинности AD используется следующая команда:

   ```bash
   azdata login --endpoint https://<control_domain_name>:30080 --auth ad
   ```

1. Выполните команду [`azdata bdc endpoint list`](../azdata/reference/reference-azdata-bdc-endpoint.md), чтобы получить список с описанием каждой конечной точки и соответствующими значениями IP-адреса и порта. 

   ```bash
   azdata bdc endpoint list -o table
   ```

   Следующий список содержит пример выходных данных этой команды.

   ```output
   Description                                             Endpoint                                                   Ip              Name               Port    Protocol
   ------------------------------------------------------  ---------------------------------------------------------  --------------  -----------------  ------  ----------
   Gateway to access HDFS files, Spark                     https://11.111.111.111:30443                               11.111.111.111  gateway            30443   https
   Spark Jobs Management and Monitoring Dashboard          https://11.111.111.111:30443/gateway/default/sparkhistory  11.111.111.111  spark-history      30443   https
   Spark Diagnostics and Monitoring Dashboard              https://11.111.111.111:30443/gateway/default/yarn          11.111.111.111  yarn-ui            30443   https
   Application Proxy                                       https://11.111.111.111:30778                               11.111.111.111  app-proxy          30778   https
   Management Proxy                                        https://11.111.111.111:30777                               11.111.111.111  mgmtproxy          30777   https
   Log Search Dashboard                                    https://11.111.111.111:30777/kibana                        11.111.111.111  logsui             30777   https
   Metrics Dashboard                                       https://11.111.111.111:30777/grafana                       11.111.111.111  metricsui          30777   https
   Cluster Management Service                              https://11.111.111.111:30080                               11.111.111.111  controller         30080   https
   SQL Server Master Instance Front-End                    11.111.111.111,31433                                       11.111.111.111  sql-server-master  31433   tcp
   HDFS File System Proxy                                  https://11.111.111.111:30443/gateway/default/webhdfs/v1    11.111.111.111  webhdfs            30443   https
   Proxy for running Spark statements, jobs, applications  https://11.111.111.111:30443/gateway/default/livy/v1       11.111.111.111  livy               30443   https
   ```

### <a name="view-cluster-status"></a>Просмотр состояния кластера

Проверить состояние кластера можно с помощью команды [`azdata bdc status show`](../azdata/reference/reference-azdata-bdc-status.md).

```bash
azdata bdc status show
```

> [!TIP]
> Чтобы выполнить команды состояния, нужно сначала войти в систему с помощью команды **azdata login**, которая была приведена в предыдущем разделе о конечных точках.

Ниже приведен пример выходных данных этой команды.

```output
 Bdc: ready                                                                                                                                                                                                          Health Status:  healthy
 ===========================================================================================================================================================================================================================================
 Services: ready                                                                                                                                                                                                     Health Status:  healthy
 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 Servicename    State    Healthstatus    Details

 spark          ready    healthy         -
 sql            ready    healthy         -
 hdfs           ready    healthy         -
 control        ready    healthy         -
 gateway        ready    healthy         -
 app            ready    healthy         -


 Spark Services: ready                                                                                                                                                                                               Health Status:  healthy
 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 Resourcename    State    Healthstatus    Details

 sparkhead       ready    healthy         StatefulSet sparkhead is healthy
 storage-0       ready    healthy         StatefulSet storage-0 is healthy


 Sql Services: ready                                                                                                                                                                                                 Health Status:  healthy
 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 Resourcename    State    Healthstatus    Details

 master          ready    healthy         StatefulSet master is healthy
 compute-0       ready    healthy         StatefulSet compute-0 is healthy
 data-0          ready    healthy         StatefulSet data-0 is healthy
 storage-0       ready    healthy         StatefulSet storage-0 is healthy


 Hdfs Services: ready                                                                                                                                                                                                Health Status:  healthy
 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 Resourcename    State    Healthstatus    Details

 nmnode-0        ready    healthy         StatefulSet nmnode-0 is healthy
 zookeeper       ready    healthy         StatefulSet zookeeper is healthy
 storage-0       ready    healthy         StatefulSet storage-0 is healthy
 sparkhead       ready    healthy         StatefulSet sparkhead is healthy


 Control Services: ready                                                                                                                                                                                             Health Status:  healthy
 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 Resourcename    State    Healthstatus    Details

 controldb       ready    healthy         StatefulSet controldb is healthy
 control         ready    healthy         ReplicaSet control is healthy
 metricsdc       ready    healthy         DaemonSet metricsdc is healthy
 metricsui       ready    healthy         ReplicaSet metricsui is healthy
 metricsdb       ready    healthy         StatefulSet metricsdb is healthy
 logsui          ready    healthy         ReplicaSet logsui is healthy
 logsdb          ready    healthy         StatefulSet logsdb is healthy
 mgmtproxy       ready    healthy         ReplicaSet mgmtproxy is healthy
 controlwd       ready    healthy         ReplicaSet controlwd is healthy


 Gateway Services: ready                                                                                                                                                                                             Health Status:  healthy
 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 Resourcename    State    Healthstatus    Details

 gateway         ready    healthy         StatefulSet gateway is healthy


 App Services: ready                                                                                                                                                                                                 Health Status:  healthy
 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 Resourcename    State    Healthstatus    Details

 appproxy        ready    healthy         ReplicaSet appproxy is healthy
```

### <a name="view-specific-resource-status"></a>Просмотр состояния конкретного ресурса

Состояние конкретного ресурса в кластере можно просмотреть с помощью команды [azdata bdc status show](../azdata/reference/reference-azdata-bdc-status.md). При использовании этой команды можно фильтровать результаты с помощью параметра `--resource`. Ниже приведены некоторые примеры входных данных для параметра `--resource`.

- master
- управляющие
- compute-0
- storage-0
- gateway

Например, следующая команда отображает состояние пула носителей.

```bash
azdata bdc status show --all --resource storage-0
```

Чтобы просмотреть состояние всех компонентов, в которых запущена определенная служба, необходимо использовать соответствующую группу команд `azdata bdc <serviceName> status show`. Пример:

- azdata bdc sql status show --all
- azdata bdc hdfs status show --all
- azdata bdc spark status show --all

Пример выходных данных:

```output
  Storage-0: ready                                                                                                                                                                                                    Health Status:  healthy
 ===========================================================================================================================================================================================================================================
 Instances: running                                                                                                                                                                                                  Health Status:  healthy
 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 Instancename    State    Healthstatus    Details

 storage-0-0     running  healthy         Pod storage-0-0 is healthy
 storage-0-1     running  healthy         Pod storage-0-1 is healthy


 Dashboards
 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 Name            Url

 nodeMetricsUrl  https://13.91.50.9:30777/api/v1/bdc/instances/storage-0-1/status/nodemetrics/ui
 sqlMetricsUrl   https://13.91.50.9:30777/api/v1/bdc/instances/storage-0-1/status/sqlmetrics/ui
 logsUrl         https://13.91.50.9:30777/api/v1/bdc/instances/storage-0-1/status/logs/ui
 ```

> [!TIP]
> Для получения дополнительных сведений о работоспособности, включая ссылки на панели мониторинга метрик и журналов, соответствующие конкретному экземпляру, выполните команду status с параметрами `--all`. Ниже приведен пример выходных данных при использовании параметров `--all`.

```output
 Spark: ready                                                                                                                                                                                                        Health Status:  healthy
 ===========================================================================================================================================================================================================================================
 Resources: ready                                                                                                                                                                                                    Health Status:  healthy
 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 Resourcename    State    Healthstatus    Details

 sparkhead       ready    healthy         StatefulSet sparkhead is healthy
 storage-0       ready    healthy         StatefulSet storage-0 is healthy


 Sparkhead Resources: running                                                                                                                                                                                        Health Status:  healthy
 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 Instancename    State    Healthstatus    Details

 sparkhead-0     running  healthy         Pod sparkhead-0 is healthy
 sparkhead-1     running  healthy         Pod sparkhead-1 is healthy


      Dashboards
      --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
      Name            Url

      nodeMetricsUrl  https://13.91.50.9:30777/api/v1/bdc/instances/sparkhead-1/status/nodemetrics/ui
      sqlMetricsUrl   https://13.91.50.9:30777/api/v1/bdc/instances/sparkhead-1/status/sqlmetrics/ui
      logsUrl         https://13.91.50.9:30777/api/v1/bdc/instances/sparkhead-1/status/logs/ui


 Storage-0 Resources: running                                                                                                                                                                                        Health Status:  healthy
 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 Instancename    State    Healthstatus    Details

 storage-0-0     running  healthy         Pod storage-0-0 is healthy
 storage-0-1     running  healthy         Pod storage-0-1 is healthy


      Dashboards
      --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
      Name            Url

      nodeMetricsUrl  https://13.91.50.9:30777/api/v1/bdc/instances/storage-0-1/status/nodemetrics/ui
      sqlMetricsUrl   https://13.91.50.9:30777/api/v1/bdc/instances/storage-0-1/status/sqlmetrics/ui
      logsUrl         https://13.91.50.9:30777/api/v1/bdc/instances/storage-0-1/status/logs/ui
```

### <a name="view-controller-status"></a>Просмотр состояния контроллера

Состояние контроллера можно увидеть с помощью команды [`azdata bdc control status show`](../azdata/reference/reference-azdata-bdc-control-status.md). Она предоставляет аналогичные ссылки на панели мониторинга, связанные с компонентами контроллера в кластере больших данных.


## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения о [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ss-nover.md)] см. в статье [Что такое [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ver15.md)]?](big-data-cluster-overview.md).