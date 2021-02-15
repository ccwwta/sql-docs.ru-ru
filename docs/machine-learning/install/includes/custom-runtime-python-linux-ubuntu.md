---
ms.prod: sql
ms.technology: machine-learning-services
ms.date: 02/08/2021
ms.topic: include
author: dphansen
ms.author: davidph
ms.openlocfilehash: 0c0efdc599574748112c1d5909404603de24da2c
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100072948"
---
## <a name="install-language-extensions"></a>Установка расширений языка

> [!NOTE]
> Если в SQL Server 2019 установлены [Службы машинного обучения](../../sql-server-machine-learning-services.md), значит, пакет **mssql-server-extensibility** для расширений языка уже установлен и этот шаг можно пропустить.

Выполните приведенные ниже команды, чтобы установить [расширения языка SQL Server](../../../language-extensions/language-extensions-overview.md) для Ubuntu Linux, которые используются в настраиваемой среде выполнения Python.

1. Если возможно, перед установкой выполните эту команду для обновления пакетов в системе.

    ```bash
    # Install as root or sudo
    sudo apt-get update
    ```

1. Ubuntu может не иметь параметр https apt transport. Чтобы установить его, выполните приведенную ниже команду.

    ```bash
    # Install as root or sudo
    apt-get install apt-transport-https
    ```

1. Установите **mssql-server-extensibility** с помощью этой команды.

    ```bash
    # Install as root or sudo
    sudo apt-get install mssql-server-extensibility
    ```

## <a name="install-python-37-and-pandas"></a>Установка Python 3.7 и Pandas

Расширение языка Python, используемое для настраиваемой среды выполнения Python, сейчас поддерживает только [Python 3.7](https://www.python.org/). Если вы хотите использовать другую версию Python, выполните инструкции из [репозитория расширения языка Python](https://github.com/microsoft/sql-server-language-extensions/tree/master/language-extensions/python), чтобы изменить и скомпилировать расширение.

1. Чтобы установить Python 3.7, выполните приведенные ниже команды.

    ```bash
    # Install python3.7 and the corresponding library:
    sudo add-apt-repository ppa:deadsnakes/ppa
    sudo apt-get update
    sudo apt-get install python3.7 python3-pip libpython3.7
    ```

1. Чтобы установить пакет pandas, выполните приведенную ниже команду.

    ```bash
    # Install pandas to /usr/lib:
    sudo python3.7 -m pip install pandas -t /usr/lib/python3.7/dist-packages
    ```
