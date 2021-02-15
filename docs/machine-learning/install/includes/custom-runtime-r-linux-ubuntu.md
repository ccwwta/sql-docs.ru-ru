---
ms.prod: sql
ms.technology: machine-learning-services
ms.date: 02/08/2021
ms.topic: include
author: dphansen
ms.author: davidph
ms.openlocfilehash: 83b39be5be128ba4fbda17765a7b67deead2c80c
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100072786"
---
## <a name="install-language-extensions"></a>Установка расширений языка

> [!NOTE]
> Если в SQL Server 2019 установлены [Службы машинного обучения](../../sql-server-machine-learning-services.md), значит, пакет **mssql-server-extensibility** для расширений языка уже установлен и этот шаг можно пропустить.

Выполните приведенные ниже команды, чтобы установить [расширения языка SQL Server](../../../language-extensions/language-extensions-overview.md) для Ubuntu Linux, которые используются в настраиваемой среде выполнения R.

1. Если возможно, перед установкой выполните эту команду для обновления пакетов в системе.

    ```bash
    # Install as root or sudo
    sudo apt-get update
    ```

1. Установите **mssql-server-extensibility** с помощью этой команды.

    ```bash
    # Install as root or sudo
    sudo apt-get install mssql-server-extensibility
    ```

## <a name="install-r"></a>Установка R

1. Если установлены [Службы машинного обучения](../../sql-server-machine-learning-services.md), среда R уже установлена в `/opt/microsoft/ropen/3.5.2/lib64/R`. Если вы хотите использовать этот путь в качестве R_HOME, данный шаг можно пропустить.

    Если вы хотите использовать другую среду выполнения R, то перед продолжением установки новой версии необходимо удалить `microsoft-r-open-mro`.

    ```bash
    sudo apt remove microsoft-r-open-mro-3.5.2
    ```

1. Установите [R (версии 3.3 или более поздней)](https://www.r-project.org/) для Ubuntu. По умолчанию R устанавливается в папку **/usr/lib/R**. Этот путь — ваш **R_HOME**. Если вы установили R в другом месте, зафиксируйте этот путь в качестве **R_HOME**.

    Ниже приведены примеры инструкций для Ubuntu. Измените URL-адрес репозитория ниже для вашей версии R.

    ```bash
    export DEBIAN_FRONTEND=noninteractive
    sudo apt-get update
    sudo apt-get --no-install-recommends -y install curl zip unzip apt-transport-https libstdc++6
    
    # Add R CRAN repository. This repository works for R 4.0.x.
    #
    sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9
    sudo add-apt-repository 'deb https://cloud.r-project.org/bin/linux/ubuntu xenial-cran40/'
    sudo apt-get update
    
    # Install R runtime.
    #
    sudo apt-get -y install r-base-core
    ```
