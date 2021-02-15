---
ms.prod: sql
ms.technology: machine-learning-services
ms.date: 02/08/2021
ms.topic: include
author: dphansen
ms.author: davidph
ms.openlocfilehash: a10c54f61151835692f2bc05de440062fe2f3cfb
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100072795"
---
## <a name="install-language-extensions"></a>Установка расширений языка

> [!NOTE]
> Если в SQL Server 2019 установлены [Службы машинного обучения](../../sql-server-machine-learning-services.md), значит, пакет **mssql-server-extensibility** для расширений языка уже установлен и этот шаг можно пропустить.

Выполните приведенную ниже команду, чтобы установить [расширения языка SQL Server](../../../language-extensions/language-extensions-overview.md) для SUSE Linux Enterprise Server (SLES), которые используются в настраиваемой среде выполнения R.

```bash
# Install as root or sudo
sudo zypper install mssql-server-extensibility
```

## <a name="install-r"></a>Установка R

1. Если установлены [Службы машинного обучения](../../sql-server-machine-learning-services.md), среда R уже установлена в `/opt/microsoft/ropen/3.5.2/lib64/R`. Если вы хотите использовать этот путь в качестве R_HOME, данный шаг можно пропустить.

    Если вы хотите использовать другую среду выполнения R, то перед продолжением установки новой версии необходимо удалить `microsoft-r-open-mro`.

    ```bash
    sudo zypper remove microsoft-r-open-mro-3.5.2
    ```

1. Установите [R (версии 3.3 или более поздней)](https://www.r-project.org/) для SUSE Linux Enterprise Server (SLES). По умолчанию R устанавливается в папку **/usr/lib/R**. Этот путь — ваш **R_HOME**. Если вы установили R в другом месте, зафиксируйте этот путь в качестве **R_HOME**.
