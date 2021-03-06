---
description: Параметры проекта (база данных SQL Azure) (Акцесстоскл)
title: Параметры проекта (база данных SQL Azure) (Акцесстоскл) | Документация Майкрософт
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Project Settings dialog box, SQL Azure
- SQL Azure settings
ms.assetid: bbb8a204-d0e4-4f0b-9709-271feb1f136e
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: 6fa8b7f9940327d3a45c3b4f349892ae253f4738
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100066459"
---
# <a name="project-settings-azure-sql-database-accesstosql"></a>Параметры проекта (база данных SQL Azure) (Акцесстоскл)
Параметры проекта SQL Azure позволяют настроить суффикс базы данных SQL Azure для добавления в диалоговом окне подключения, а также разрешить использование механизма пульса в SQL Azure подключении.  
  
Панель SQL Azure доступна в диалоговых окнах **Параметры проекта** и **Параметры проекта по умолчанию** .  
  
-   Используйте диалоговое окно Параметры проекта, чтобы задать параметры конфигурации для текущего проекта. Чтобы получить доступ к параметрам SQL Azure, в меню **Сервис** выберите **Параметры проекта**, щелкните **Общие** в нижней части левой панели, а затем выберите **SQL Azure**.  
  
-   Используйте диалоговое окно Параметры проекта по умолчанию, чтобы задать параметры конфигурации для всех проектов. Чтобы получить доступ к параметрам SQL Azure, в меню **Сервис** выберите пункт **Параметры**, в поле со списком **версия целевого объекта миграции** выберите тип проекта "SQL Azure", чтобы получить доступ к параметрам в SQL Azure панели, щелкните **Общие** в нижней части левой панели, а затем выберите **SQL Azure**.  
  
## <a name="options"></a>Параметры  
  
## <a name="connectivity"></a>Соединение  
**Интервал пульса**  
  
Указывает интервал времени, используемый для механизма пульса, чтобы поддерживать подключение SQL Azure в формате "минуты: секунды".  
  
**Значение по умолчанию**: ' 4:45 '  
  
Значение должно быть указано в формате "м:СС" (например, "4:45" или "0:50").  
  
**Суффикс SQL Azure Server**  
  
Указывает суффикс сервера SQL Azure  
  
**Значение по умолчанию**: "Database.Windows.NET".  
  
