---
ms.prod: sql
ms.technology: machine-learning-services
ms.date: 02/08/2021
ms.topic: include
author: dphansen
ms.author: davidph
ms.openlocfilehash: c6d15087150e914e62b5d19951715198ced47512
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100072924"
---
## <a name="install-language-extensions"></a>Установка расширений языка

> [!NOTE]
> Если в SQL Server 2019 установлены [Службы машинного обучения](../../sql-server-machine-learning-services.md), значит, пакет **mssql-server-extensibility** для расширений языка уже установлен и этот шаг можно пропустить.

Выполните приведенную ниже команду, чтобы установить [расширения языка SQL Server](../../../language-extensions/language-extensions-overview.md) для Red Hat Enterprise Linux (RHEL), которые используются в настраиваемой среде выполнения Python.

```bash
# Install as root or sudo
sudo yum install mssql-server-extensibility
```

## <a name="install-python-37-and-pandas"></a>Установка Python 3.7 и Pandas

Расширение языка Python, используемое для настраиваемой среды выполнения Python, сейчас поддерживает только [Python 3.7](https://www.python.org/). Если вы хотите использовать другую версию Python, выполните инструкции из [репозитория расширения языка Python](https://github.com/microsoft/sql-server-language-extensions/tree/master/language-extensions/python), чтобы изменить и скомпилировать расширение.

1. Чтобы установить Python 3.7, выполните приведенные ниже команды.

    ```bash
    # Install python3.7 and the corresponding library:
    yum install gcc openssl-devel bzip2-devel libffi-devel zlib-devel
    
    cd /usr/src
    wget https://www.python.org/ftp/python/3.7.9/Python-3.7.9.tgz
    tar xzf Python-3.7.9.tgz
    
    cd Python-3.7.9
    ./configure --enable-optimizations --prefix=/usr
    make altinstall
    ```

1. Чтобы установить пакет pandas, выполните приведенную ниже команду.

    ```bash
    # Install pandas to /usr/lib:
    sudo python3.7 -m pip install pandas -t /usr/lib/python3.7/dist-packages
    ```
