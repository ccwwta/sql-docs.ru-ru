---
title: Система управления версиями
description: Azure Data Studio поддерживает Git в качестве системы управления версиями (SCM). Узнайте, как открыть существующий репозиторий Git и как инициализировать новый.
ms.prod: azure-data-studio
ms.technology: azure-data-studio
ms.topic: conceptual
author: markingmyname
ms.author: maghan
ms.reviewer: alayu, sstein
ms.custom: seodec18
ms.date: 09/24/2019
ms.openlocfilehash: 014376dd56045b9e5ef440054ae2c1d1df836cad
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100040024"
---
# <a name="source-control-in-azure-data-studio"></a>Система управления версиями в Azure Data Studio

Azure Data Studio поддерживает Git для управления версиями/исходным кодом.

## <a name="git-support-in-azure-data-studio"></a>Поддержка Git в Azure Data Studio

Azure Data Studio поставляется вместе с диспетчером системы управления версиями (SCM) Git, но вам все равно нужно [установить Git (версии 2.0.0 или более поздней)](https://git-scm.com/download), чтобы получить доступ к этим функциям.

## <a name="open-an-existing-git-repository"></a>Открытие существующего репозитория Git

1. В меню **Файл** выберите **Открыть папку...**
2. Перейдите в папку с файлами, отслеживаемыми Git, и щелкните элемент **Выбрать папку**. Здесь можно выбрать вложенные папки в локальном репозитории.

## <a name="initialize-a-new-git-repository"></a>Инициализация нового репозитория Git

1. Выберите **Система управления версиями**, а затем щелкните значок Git.

   ![Значок Git для системы управления версиями](media/source-control/source-control.png)

1. Введите путь к папке, которую нужно инициализировать в качестве репозитория Git, и нажмите клавишу **ВВОД**.

   ![инициализировать репозиторий Git](media/source-control/initialize-git-repository.png)

## <a name="working-with-git-repositories"></a>Работа с репозиториями Git

Azure Data Studio наследует свою реализацию Git от VS Code, но сейчас не поддерживает дополнительные поставщики SCM. Дополнительные сведения о работе с Git после открытия или инициализации репозитория см. в разделе [Поддержка Git в VS Code](https://code.visualstudio.com/docs/editor/versioncontrol#_git-support).

## <a name="additional-resources"></a>Дополнительные ресурсы

- [Документация по Git](https://git-scm.com/documentation)
