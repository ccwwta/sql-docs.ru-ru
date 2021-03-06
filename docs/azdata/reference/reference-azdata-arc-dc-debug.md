---
title: Справочник по azdata arc dc debug
titleSuffix: SQL Server big data clusters
description: Справочная статья по командам azdata arc dc debug.
author: MikeRayMSFT
ms.author: mikeray
ms.reviewer: seanw
ms.date: 09/22/2020
ms.topic: reference
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: 3979dbd8561eeedf3e5c0ab03a51b04b2bd73674
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100052685"
---
# <a name="azdata-arc-dc-debug"></a>azdata arc dc debug

Применяется к [!INCLUDE [azure-data-cli-azdata](../../includes/azure-data-cli-azdata.md)]

В следующей статье приводятся справочные сведения по командам **sql** в средстве **azdata**. Дополнительные сведения о других командах **azdata** см. в [справочнике по azdata](reference-azdata.md).

## <a name="commands"></a>Команды

|Команда|Описание|
| --- | --- |
[azdata arc dc debug copy-logs](#azdata-arc-dc-debug-copy-logs) | Копирование журналов.
[azdata arc dc debug dump](#azdata-arc-dc-debug-dump) | Создание дампа памяти.
## <a name="azdata-arc-dc-debug-copy-logs"></a>azdata arc dc debug copy-logs
Копирование журналов отладки из контроллера данных. В системе должна быть конфигурация Kubernetes.
```bash
azdata arc dc debug copy-logs --namespace -ns 
                              [--container -c]  
                              
[--target-folder -d]  
                              
[--pod]  
                              
[--resource-kind -rk]  
                              
[--resource-name -rn]  
                              
[--timeout -t]  
                              
[--skip-compress -sc]  
                              
[--exclude-dumps -ed]
```
### <a name="required-parameters"></a>Обязательные параметры
#### `--namespace -ns`
Пространство имен Kubernetes контроллера данных.
### <a name="optional-parameters"></a>Необязательные параметры
#### `--container -c`
Копирование журналов для контейнеров с одинаковыми именами. Необязательный параметр. По умолчанию копируются журналы для всех контейнеров. Нельзя указывать несколько раз. Если этот параметр указан несколько раз, используется последний параметр.
#### `--target-folder -d`
Путь к конечной папке, в которую должны копироваться журналы. Необязательный параметр. По умолчанию результаты помещаются в локальную папку.  Нельзя указывать несколько раз. Если этот параметр указан несколько раз, используется последний параметр.
#### `--pod`
Копирование журналов для объектов pod с одинаковыми именами. Необязательный параметр. По умолчанию копируются журналы для всех объектов pod. Нельзя указывать несколько раз. Если этот параметр указан несколько раз, используется последний параметр.
#### `--resource-kind -rk`
Копирование журналов для ресурса определенного типа. Нельзя указывать несколько раз. Если этот параметр указан несколько раз, используется последний параметр. Если указан этот параметр, то для определения ресурса также должен быть указан параметр --resource-name.
#### `--resource-name -rn`
Копирование журналов для ресурса указанного имени. Нельзя указывать несколько раз. Если этот параметр указан несколько раз, используется последний параметр. Если указан этот параметр, то для определения ресурса также должен быть указан параметр --resource-kind.
#### `--timeout -t`
Время ожидания завершения команды в секундах. Значение по умолчанию — 0, что означает неограниченный срок.
#### `--skip-compress -sc`
Следует ли пропустить сжатие папки результатов. Значение по умолчанию — false, которое сжимает папку результатов.
#### `--exclude-dumps -ed`
Следует ли исключать дампы из папки результатов. Значение по умолчанию — false, включающее дампы.
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
## <a name="azdata-arc-dc-debug-dump"></a>azdata arc dc debug dump
Создание дампа памяти и его копирование из контейнера. В системе должна быть конфигурация Kubernetes.
```bash
azdata arc dc debug dump --namespace -ns 
                         [--container -c]  
                         
[--target-folder -d]
```
### <a name="required-parameters"></a>Необходимые параметры
#### `--namespace -ns`
Пространство имен Kubernetes контроллера данных.
### <a name="optional-parameters"></a>Необязательные параметры
#### `--container -c`
Целевой контейнер, запускаемый для создания дампа запущенных процессов.
`controller`
#### `--target-folder -d`
Целевая папка для копирования дампа. `./output/dump`
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

Дополнительные сведения об установке инструмента **azdata** см. в разделе [Установка azdata](..\install\deploy-install-azdata.md).

