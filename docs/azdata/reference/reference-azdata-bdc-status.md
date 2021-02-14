---
title: Справочник по azdata bdc status
titleSuffix: SQL Server big data clusters
description: Справочная статья по командам azdata bdc status.
author: MikeRayMSFT
ms.author: mikeray
ms.reviewer: seanw
ms.date: 09/22/2020
ms.topic: reference
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: 1b68597661d889043a6a0b4a182209b6769f736c
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100048744"
---
# <a name="azdata-bdc-status"></a>azdata bdc status

Применяется к [!INCLUDE [azure-data-cli-azdata](../../includes/azure-data-cli-azdata.md)]

В следующей статье приводятся справочные сведения по командам **sql** в средстве **azdata**. Дополнительные сведения о других командах **azdata** см. в [справочнике по azdata](reference-azdata.md).

## <a name="commands"></a>Команды

|Команда|Описание|
| --- | --- |
[azdata bdc status show](#azdata-bdc-status-show) | Показывает состояние BDC.
## <a name="azdata-bdc-status-show"></a>azdata bdc status show
Показывает состояние BDC.
```bash
azdata bdc status show [--resource -r] 
                       [--all -a]
```
### <a name="examples"></a>Примеры
Состояние кластера больших данных, куда пользователь выполнил вход.
```bash
azdata bdc status show
```
Состояние BDC со всеми включенными экземплярами ресурсов.
```bash
azdata bdc status show --all
```
Состояние BDC служб, включая ресурс управления.
```bash
azdata bdc status show --resource control
```
### <a name="optional-parameters"></a>Необязательные параметры
#### `--resource -r`
Получение служб, связанных с этим ресурсом.
#### `--all -a`
Отображение всех экземпляров каждого ресурса в службах.
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

