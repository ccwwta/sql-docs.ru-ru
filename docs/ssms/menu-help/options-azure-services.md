---
title: Страница "Параметры SQL Server" — службы Azure
description: Параметры (службы Azure)
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Azure_Services.Azure_Cloud
dev_langs:
- TSQL
author: markingmyname
ms.author: maghan
ms.date: 01/15/2021
ms.openlocfilehash: 0983317d1d5c59e486764532708c566bb740000a
ms.sourcegitcommit: 23649428528346930d7d5b8be7da3dcf1a2b3190
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "98245711"
---
# <a name="options-azure-services"></a>Параметры (службы Azure)

Используйте эту страницу, чтобы указать параметры, связанные с облачными службами Azure. Чтобы открыть это диалоговое окно, перейдите в меню **Сервис > Параметры > Службы Azure** вверху.

## <a name="miscellaneous"></a>Прочее

| Параметр | Сведения | Описание |
|--------|-------------|-------------|
| Уровень трассировки окна вывода ADAL | **Сведения**. <br> **None** <br> **Подробный** <br> **Предупреждение** | Уровень трассировки событий входа Azure Active Directory (AAD) для отправки в окно вывода. |
| URL-адрес портала Фабрики данных Azure | `https://adf.azure.com` | Указывает URL-адрес портала Фабрики данных Azure. |
| Включение условного доступа к Базе данных SQL Azure (ЭКСПЕРИМЕНТАЛЬНАЯ ВЕРСИЯ) | **True** <br> **False** | ЭКСПЕРИМЕНТАЛЬНАЯ ВЕРСИЯ: если значение — true, запрашивает маркеры доступа для Базы данных SQL Azure с утверждением для обращения к выбранному серверу. Чтобы параметр вступил в силу, может потребоваться перезагрузка SSMS. |
| Конечная точка коллекции | `https://gallery.azure.com` | Указывает конечную точку коллекции Resource Manager шаблонов развертывания. |
| Аудитория графа | `https://graph.windows.net` | Идентификатор ресурса конечной точки графа. |
| Конечная точка графа | `https://graph.windows.net` | Указывает URL-адрес для запросов графа Azure Active Directory. |
| URL-адрес портала управления | `https://portal.azure.com` | Указывает URL-адрес портала управления. |
| URL-адрес файла параметров публикации | `https://go.microsoft.com/fwlink/?LinkID=335839` | Указывает URL-адрес, по которому можно скачать файл `.publishsettings`. |
| Имя субъекта-службы Базы данных SQL | `https://database.windows.net/` | Имя субъекта-службы Базы данных SQL Azure для получения маркера при использовании проверки подлинности AAD. Также аудитория JSON Web Token (JWT) для синтаксического анализа и проверки JSON Web Token (JWT) на стороне сервера. |

## <a name="resource-management"></a>Управление ресурсами

| Параметр | Сведения | Описание |
|--------|-------------|-------------|
| Центр Active Directory | `https://login.microsoftonline.com` | Указывает базовый центр для проверки подлинности Azure Active Directory (AAD). |
| Идентификатор ресурса конечной точки службы Active Directory | `https://management.core.windows.net` | Указывает аудиторию для маркеров, которые проверяют подлинность запросов к Azure Resource Manager (ARM) или конечным точкам Управления службами (RDFE). |
| Конечная точка Resource Manager | `https://management.azure.com` | Указывает URL-адрес для запросов к Управлению ресурсами. |
| Конечная точка службы | `https://management.core.windows.net` | Указывает конечную точку для запросов к Управлению службами. |

## <a name="select-an-azure-cloud"></a>Выбор облака Azure

| Параметр | Сведения | Описание |
|--------|-------------|-------------|
| Имя | **Облако Azure для Китая** <br><br> **Облако Azure** <br><br> **Облако Azure для Германии.** <br><br> **Azure для US Gov организаций.** <br><br> **Custom** | Выберите облако Azure, к которому Management Studio подключается для обнаружения ресурсов и управления ими. Выберите **Настраиваемые**, чтобы указать собственные URL-адреса и DNS-суффиксы. |

## <a name="service-addresses"></a>Адреса служб

| Параметр | Сведения | Описание |
|--------|-------------|-------------|
| Конечная точка служб Azure Data Lake | `azuredatalakeanalytics.net` | Указывает каталог Azure Data Lake Analytics и суффикс конечной точки задания. |
| Конечная точка файловой системы Azure Data Lake Store | `azuredatalakestore.net` | Указывает суффикс конечной точки файловой системы Azure Data Lake Store. | 
| Аудитория Azure Key Vault | `https://vault.azure.net` | Указывает аудиторию для маркеров доступа, которые разрешают запросы к службам Key Vault. |
| DNS-суффикс Azure Key Vault | `vault.azure.net` | Указывает суффикс доменного имени для серверов Azure Key Vault. |
| DNS-суффикс Базы данных SQL | `database.windows.net` | Указывает суффикс доменного имени для серверов Базы данных SQL Azure. |
| Конечная точка хранилища | `core.windows.net` | Указывает конечную точку для доступа к хранилищу. Параметр применим к большим двоичным объектам, таблицам, очередям и хранилищам файлов. |
| DNS-суффикс Диспетчера трафика | `trafficmanager.net` | Указывает суффикс доменного имени для служб Диспетчера трафика Azure. |