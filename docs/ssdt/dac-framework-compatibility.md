---
title: Совместимость с платформой приложения уровня данных
description: Ознакомьтесь с сообщением об ошибке, которое может появиться при попытке выполнения действий в SQL Server Data Tools (SSDT), использующих несовместимые версии платформы DAC Framework.
ms.prod: sql
ms.technology: ssdt
ms.topic: conceptual
ms.assetid: 5f8e7f4a-f157-442a-8fe5-32b8774776dc
author: markingmyname
ms.author: maghan
ms.reviewer: “”
ms.custom: seo-lt-2019
ms.date: 02/09/2017
ms.openlocfilehash: 6ffaac3a90a7a190a156ec06127bee240b23f5b5
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100079595"
---
# <a name="dac-framework-compatibility"></a>Совместимость с платформой приложения уровня данных

При попытке выполнить действие, которое использует платформу приложений уровня данных, SQL Server Data Tools (SSDT) проверяет версию DACFx на компьютере. Если SSDT не работает с установленной версией DACFx, отображается следующая ошибка:

**На этом компьютере установлены несовместимые версии SQL Server Data Tools и компонентов среды выполнения базы данных**

Можно загрузить более новую версию SSDT со страницы [Установка последней версии SQL Server Data Tools](./download-sql-server-data-tools-ssdt.md).