---
title: Справочник по состояниям шлюза bdc azdata
titleSuffix: SQL Server big data clusters
description: Справочная статья по командам состояния шлюза bdc azdata.
author: MikeRayMSFT
ms.author: mikeray
ms.reviewer: seanw
ms.date: 09/22/2020
ms.topic: reference
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: ef05cb490757b1b21b9f3faa7cdb0b881a0089ba
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100052475"
---
# <a name="azdata-bdc-gateway-status"></a>Состояние шлюза bdc azdata

Применяется к [!INCLUDE [azure-data-cli-azdata](../../includes/azure-data-cli-azdata.md)]

В следующей статье приводятся справочные сведения по командам **sql** в средстве **azdata**. Дополнительные сведения о других командах **azdata** см. в [справочнике по azdata](reference-azdata.md).

## <a name="commands"></a>Команды

|Команда|Описание|
| --- | --- |
[Показать состояние шлюза bdc azdata](#azdata-bdc-gateway-status-show) | Состояние службы шлюза.
## <a name="azdata-bdc-gateway-status-show"></a>Показать состояние шлюза bdc azdata
Состояние службы шлюза.
```bash
azdata bdc gateway status show [--resource -r] 
                               [--all -a]
```
### <a name="examples"></a>Примеры
Получение состояния службы шлюза.
```bash
azdata bdc gateway status show
```
Получение состояния службы шлюза со всеми экземплярами.
```bash
azdata bdc gateway status show --all
```
Получение состояния ресурса шлюза в службе шлюза.
```bash
azdata bdc gateway status show --resource gateway
```
### <a name="optional-parameters"></a>Необязательные параметры
#### `--resource -r`
Получение ресурса в этой службе.
#### `--all -a`
Отображение всех экземпляров каждого ресурса в службе.
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

Дополнительные сведения об установке средства **azdata** см. в статье [Установка azdata](..\install\deploy-install-azdata.md).

