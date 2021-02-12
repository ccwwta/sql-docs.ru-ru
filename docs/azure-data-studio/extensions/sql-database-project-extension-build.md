---
title: Сборка и публикация проекта
description: Сборка и публикация с помощью расширения проектов баз данных SQL Server
ms.prod: azure-data-studio
ms.technology: azure-data-studio
ms.topic: conceptual
author: dzsquared
ms.author: drskwier
ms.reviewer: maghan, sstein
ms.custom: ''
ms.date: 06/25/2020
ms.openlocfilehash: 8bcc0e9d54c98c83e184c3ff957dbf35082ba673
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100048418"
---
# <a name="build-and-publish-a-project"></a>Сборка и публикация проекта

Процесс сборки в расширении проектов баз данных SQL (предварительная версия) для Azure Data Studio позволяет создавать *DACPAC* в средах Windows, macOS и Linux. Проект затем можно развернуть в локальной или облачной среде с помощью процесса публикации.

## <a name="prerequisites"></a>Предварительные требования

- Установите и настройте [расширение проектов баз данных SQL для Azure Data Studio](sql-database-project-extension.md).

## <a name="build-a-database-project"></a>Создание проекта базы данных

 В мини-приложении **Проекты** **Обозревателя** щелкните правой кнопкой мыши корневой узел *.sqlproj* и выберите **Сборка**.

 Автоматически отобразится область вывода с выходными данными процесса сборки.  Успешная сборка будет завершаться следующим сообщением: 

 ``` ... exited with code: 0 ```

## <a name="publish-a-database-project"></a>Публикация проекта базы данных

После успешной компиляции проекта с помощью процесса сборки базу данных можно опубликовать в экземпляре SQL Server. Чтобы опубликовать проект базы данных, в мини-приложении **Проекты** **Обозревателя** щелкните правой кнопкой мыши корневой узел *.sqlproj* и выберите **Опубликовать**.

В появившемся диалоговом окне **публикации базы данных** укажите соединение сервера и имя создаваемой базы данных.

## <a name="next-steps"></a>Дальнейшие действия

- [Расширение проектов баз данных SQL для Azure Data Studio](sql-database-project-extension.md)
- [Создание проектов баз данных SQL из командной строки](sql-database-project-extension-build-from-command-line.md)
