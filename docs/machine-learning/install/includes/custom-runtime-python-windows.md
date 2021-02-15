---
ms.prod: sql
ms.technology: machine-learning-services
ms.date: 02/08/2021
ms.topic: include
author: dphansen
ms.author: davidph
ms.openlocfilehash: 9f58ddf6b58e32d40b2962b47255aba2e553acca
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100072957"
---
## <a name="prerequisites"></a>Предварительные требования

Перед установкой настраиваемой среды выполнения Python установите указанные ниже компоненты.

+ Если вы используете существующий экземпляр SQL Server, установите [накопительный пакет обновления (CU) 3 или более поздней версии](../../../database-engine/install-windows/latest-updates-for-microsoft-sql-server.md) для SQL Server 2019.

## <a name="install-language-extensions"></a>Установка расширений языка

> [!NOTE]
> Если в SQL Server 2019 установлены [Службы машинного обучения](../../sql-server-machine-learning-services.md), значит, расширения языка уже установлены и этот шаг можно пропустить.

Выполните описанные ниже действия, чтобы установить [расширения языка SQL Server](../../../language-extensions/language-extensions-overview.md), которые используются для настраиваемой среды выполнения Python.

1. Запустите мастер установки SQL Server 2019.
  
1. На вкладке **Установка** выберите параметр **Новая установка изолированного экземпляра SQL Server или добавление компонентов к существующей установке**.

1. На странице **Выбор компонентов** выберите следующие компоненты:
  
    + **Службы ядра СУБД**
  
        Чтобы использовать расширения языка с SQL Server, необходимо установить экземпляр ядра СУБД. Можно использовать новый или уже существующий экземпляр.
  
    + **Службы машинного обучения и расширения языка**

        Выберите **Службы машинного обучения и расширения языка**. Не выбирайте Python, так как настраиваемую среду выполнения Python вы установите позже.

        :::image type="content" source="../media/2019-setup-language-extensions.png" alt-text="Установка расширений языка для SQL Server 2019.":::

1. На странице **Все готово для установки** проверьте, включены ли указанные ниже компоненты, и нажмите **Установить**.
  
    + Службы ядра СУБД
    + Службы машинного обучения и расширения языка

1. Когда установка завершится, перезагрузите компьютер, если появится соответствующее предложение.

> [!IMPORTANT]
> Если вы устанавливаете новый экземпляр SQL Server 2019 с расширениями языка, обязательно установите [накопительный пакет обновления 3 или более поздней версии](../../../database-engine/install-windows/latest-updates-for-microsoft-sql-server.md), прежде чем перейти к следующему шагу.

## <a name="install-python"></a>Установка Python

Расширение языка Python, используемое для настраиваемой среды выполнения Python, сейчас поддерживает только Python 3.7. Если вы хотите использовать другую версию Python, выполните инструкции из [репозитория расширения языка Python](https://github.com/microsoft/sql-server-language-extensions/tree/master/language-extensions/python), чтобы изменить и скомпилировать расширение.

1. Скачайте [Python 3.7](https://www.python.org/downloads/windows/) для Windows и запустите программу установки на сервере.

1. Выберите **Добавить Python 3.7 в переменную PATH**, а затем выберите **Настроить установку**.

    :::image type="content" source="../media/python-install-add-to-path.png" alt-text="Установка Python 3.7 — &quot;Добавить Python 3.7 в переменную PATH&quot;":::

1. В разделе **Дополнительные компоненты** оставьте значения по умолчанию и нажмите кнопку **Далее**.

1. Выберите параметр **Установить для всех пользователей** и запишите место установки.

    :::image type="content" source="../media/python-install-for-all-users.png" alt-text="Установка Python 3.7 — &quot;Установить для всех пользователей&quot;":::

1. Выберите пункт **Установить**.

## <a name="install-pandas"></a>Установка Pandas

Установите пакет [pandas](https://pandas.pydata.org/) для Python из командной строки *с повышенными привилегиями* (запуск от имени администратора):

```bash
python.exe -m pip install pandas
```

## <a name="grant-access-to-python-folder"></a>Предоставление доступа к папке Python

Выполните приведенные ниже команды **icacls** из нового окна командной строки *с повышенными привилегиями*, чтобы предоставить разрешения на доступ для **чтения и выполнения** к папке установки Python для **службы "Панель запуска SQL Server"** и идентификатора безопасности **S-1-15-2-1** (**ALL_APPLICATION_PACKAGES**).

В приведенных ниже примерах используется расположение установки Python `C:\Program Files\Python37`. Если у вас другое расположение, измените его в команде.

1. Предоставьте разрешения **имени пользователя службы панели запуска SQL Server**.

    ```cmd
    icacls "C:\Program Files\Python37" /grant "NT Service\MSSQLLAUNCHPAD":(OI)(CI)RX /T
    ```

    Для именованного экземпляра с именем **SQL01** используется команда `icacls "C:\Program Files\Python37" /grant "NT Service\MSSQLLAUNCHPAD$SQL01":(OI)(CI)RX /T`.

2. Предоставьте разрешения **идентификатору безопасности S-1-15-2-1**.

    ```cmd
    icacls "C:\Program Files\Python37" /grant *S-1-15-2-1:(OI)(CI)RX /T
    ```

    Приведенная выше команда предоставляет разрешения идентификатору безопасности компьютера **S-1-15-2-1**, что эквивалентно разрешению **ALL APPLICATION PACKAGES** (Все пакеты приложений) в английской версии Windows. Кроме того, можно использовать `icacls "C:\Program Files\Python37" /grant "ALL APPLICATION PACKAGES":(OI)(CI)RX /T` в английской версии Windows.

## <a name="restart-sql-server-launchpad"></a>Перезапуск панели запуска SQL Server

Выполните описанные ниже действия, чтобы перезапустить службу "Панель запуска SQL Server".

1. Откройте [Диспетчер конфигурации SQL Server](../../../relational-databases/sql-server-configuration-manager.md).

1. В разделе **Службы SQL Server** щелкните элемент **Панель запуска SQL Server (MSSQLSERVER)** правой кнопкой мыши и выберите действие **Перезапустить**. Если используется именованный экземпляр, вместо **(MSSQLSERVER)** будет отображаться имя этого экземпляра.

## <a name="register-language-extension"></a>Регистрация расширения языка

Выполните описанные ниже действия, чтобы скачать и зарегистрировать расширение языка Python, которое используется для настраиваемой среды выполнения Python.

1. Скачайте файл **python-lang-extension-windows-release.zip** из [репозитория GitHub для расширений языка SQL Server](https://github.com/microsoft/sql-server-language-extensions/releases).

    Для среды разработки или тестирования также можно использовать отладочную версию (**python-lang-extension-windows-debug.zip**). Отладочная версия сохраняет в журнал подробные сведения, которые помогают изучать ошибки, и не рекомендуется для рабочих сред.

1. С помощью [Azure Data Studio](../../../azure-data-studio/what-is-azure-data-studio.md) подключитесь к экземпляру SQL Server и выполните приведенную ниже команду T-SQL, чтобы зарегистрировать расширение языка Python с помощью инструкции [CREATE EXTERNAL LANGUAGE](../../../t-sql/statements/create-external-language-transact-sql.md).

    Измените путь в этой инструкции таким образом, чтобы он указывал расположение скачанного ZIP-файла с расширением языка (**python-lang-extension-windows-release.zip**) и место установки Python (`C:\\Program Files\\Python3.7`).

    ```sql
    CREATE EXTERNAL LANGUAGE [myPython]
    FROM (CONTENT = N'C:\path\to\python-lang-extension-windows-release.zip', 
        FILE_NAME = 'pythonextension.dll', 
        ENVIRONMENT_VARIABLES = N'{"PYTHONHOME": "C:\\Program Files\\Python3.7"}');
    GO
    ```

    Выполните эту инструкцию для каждой базы данных, в которой вы намерены использовать расширение языка Python.

    > [!NOTE]
    > **Python** является зарезервированным словом, то есть вы не сможете указать такое имя для нового внешнего языка. Выберите другое имя. Например, в приведенной выше инструкции это имя **myPython**.
