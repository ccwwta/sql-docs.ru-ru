---
title: Справочник по azdata arc dc status
titleSuffix: SQL Server big data clusters
description: Справочная статья по командам azdata arc dc status.
author: MikeRayMSFT
ms.author: mikeray
ms.reviewer: seanw
ms.date: 09/22/2020
ms.topic: reference
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: 91bcda5ac4fc7cb39887698cdea19a55b47d8445
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100052675"
---
# <a name="azdata-arc-dc-status"></a>azdata arc dc status

Применяется к [!INCLUDE [azure-data-cli-azdata](../../includes/azure-data-cli-azdata.md)]

В следующей статье приводятся справочные сведения по командам **sql** в средстве **azdata**. Дополнительные сведения о других командах **azdata** см. в [справочнике по azdata](reference-azdata.md).

## <a name="commands"></a>Команды

|Команда|Описание|
| --- | --- |
[azdata arc dc status show](#azdata-arc-dc-status-show) | Показывает состояние контроллера данных.
## <a name="azdata-arc-dc-status-show"></a>azdata arc dc status show
Показывает состояние контроллера данных.
```bash
azdata arc dc status show [--namespace -ns] 
                          
```
### <a name="examples"></a>Примеры
Показывает состояние контроллера данных в определенном пространстве имен.
```bash
azdata arc dc status show --namespace <ns>
```
### <a name="optional-parameters"></a>Необязательные параметры
#### `--namespace -ns`
Пространство имен Kubernetes, в котором существует контроллер данных.
### <a name="global-arguments"></a>Глобальные аргументы
#### `--debug`
Повышение уровня детализации журнала для включения всех журналов отладки.
#### `--help -h`
Отображение этого справочного сообщения и выход.
#### `--output -o`
Формат вывода.  Допустимые значения: json, jsonc, table, tsv.  Значение по умолчанию: json.
#### `--query -q`
Строка запроса JMESPath. Дополнительные сведения и примеры см. в разделе [http://jmespath.org/](http://jmespath.org).
#### `--verbose`
Повышение уровня детализации журнала. Чтобы включить полные журналы отладки, используйте параметр --debug.

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения о других командах **azdata** см. в [справочнике по azdata](reference-azdata.md). 

Дополнительные сведения об установке средства **azdata** см. в разделе [Установка azdata](..\install\deploy-install-azdata.md).

