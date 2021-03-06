---
title: Импорт в проект базы данных
description: Узнайте, как импортировать объекты в проект базы данных из действующей базы данных, приложения уровня данных и скрипта. Узнайте об импорте зашифрованных объектов.
ms.prod: sql
ms.technology: ssdt
ms.topic: conceptual
f1_keywords:
- SQL.DATA.TOOLS.SQLPROJECTIMPORTSNAPSHOTSUMMARYDIALOG.DIALOG
- SQL.DATA.TOOLS.SQLPROJECTIMPORTDATABASESUMMARYDIALOG.DIALOG
- SQL.DATA.TOOLS.IMPORTSCRIPTWIZARD.SUMMARY
ms.assetid: d0a0a394-6cb6-416a-a25f-9babf8ba294a
author: markingmyname
ms.author: maghan
ms.reviewer: “”
ms.custom: seo-lt-2019
ms.date: 02/09/2017
ms.openlocfilehash: 0820f680382d7a126d2837c653ab7870defeb0ae
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100017934"
---
# <a name="import-into-a-database-project"></a>Импорт в проект базы данных

Функцию импорта можно использовать для заполнения проекта новыми объектами из активной базы данных или файла DACPAC либо для обновления имеющихся объектов в проекте новым определением из скрипта. Следует отметить некоторые приведенные ниже различия в поведении между этими тремя действиями.  
  
**Меню "Импорт"**  
  
![Меню импорта SSDT](../ssdt/media/ssdt-import.gif "Меню импорта SSDT")  
  
**Подразделы этого раздела**  
  
[Источник импорта: база данных или приложение уровня данных (*.dacpac)](#bkmk_import_source_db)  
  
[Источник импорта: скрипт (*.sql)](#bkmk_import_source_script)  
  
[Импорт зашифрованных объектов](#bkmk_import_encrypted)  
  
## <a name="import-source-database-or-data-tier-application-dacpac"></a><a name="bkmk_import_source_db"></a>Источник импорта: база данных или приложение уровня данных (*.dacpac)  
Возможность импорта схемы из базы данных или файла DACPAC доступна только в том случае, если в проекте еще не определены никакие объекты схемы. Это не относится к журналам рефакторинга или скриптам, выполняемым до и после развертывания.  
  
При импорте определения объектов записываются в файлы проекта с использованием параметров организации по умолчанию SSDT для новых объектов: новых файлов объектов верхнего уровня, иерархических потомков, определенных в том же файле в качестве родительского элемента, ограничений таблицы или столбца, определенных встроенным образом, где это возможно. Чтобы обеспечить более целенаправленную видимость и управление для каждого объекта, воспользуйтесь не импортом, а функцией «Сравнение схемы».  
  
Если источник импорта содержит скрипты, выполняемые до и после развертывания, журналы рефакторинга или определения переменных SQLCMD, то они будут импортированы в проект. Если проект уже содержит любой из этих объектов, импортированные файлы будут добавлены в папку проекта **Пропущенное при импорте**.  
  
**Пропущенное при импорте**  
  
![Папка SSDT "Проигнорирован При Импорте"](../ssdt/media/ssdt-ignoredonimport.gif "Папка SSDT "Проигнорирован При Импорте"")  
  
## <a name="import-source-script-sql"></a><a name="bkmk_import_source_script"></a>Источник импорта: скрипт (*.sql)  
Все объекты из источника импорта, которые *отсутствуют* в проекте, будут добавлены, а все объекты в источнике импорта, которые *присутствуют* в проекте, перезапишут соответствующие определения в проекте.  
  
> [!NOTE]  
> Известны две ошибки данного метода, которые будут исправлены в следующем выпуске:  
>   
> -   Если ограничения таблицы или столбца определены за пределами инструкции CREATE TABLE в определении таблицы проекта, то при импорте определение таблицы будет перезаписано, так что ограничение будет встроенным. Однако внешнее ограничение останется, в результате чего в проекте будут повторяющиеся ограничения.  
> -   Главные ключи или ключи шифрования базы данных из скрипта-источника, уже имеющиеся в проекте, будут дублированы при импорте. Для сборки проекта удалите повторяющиеся элементы.  
  
Процесс «Импорт из скрипта» не обрабатывает сценарии, выполняемые до или после развертывания, переменные SQLCMD и файлы журналов рефакторинга. Эти и другие неподдерживаемые конструкции, обнаруженные во время импорта, будут помещены в файл **ScriptsIgnoredOnImport.sql** в папке **Скрипты** проекта.  
  
 
## <a name="import-encrypted-objects"></a><a name="bkmk_import_encrypted"></a>Импорт зашифрованных объектов  
При импорте зашифрованных объектов в проект базы данных полный текст определения объекта не всегда может быть получен с сервера. Таким образом, поведение при импорте может быть различным при работе с данным классом объектов.  
  
Если полный текст определения получить не удается, то в скрипт помещается верхний и нижний колонтитул объекта с фиктивным текстом. Такое поведение может возникнуть при импорте или сравнении схемы, когда источником является активная база данных или файл DACPAC, извлеченный из базы данных.  
  
**Скрипт с фиктивным текстом**  
  
![Скрипт с фиктивным текстом](../ssdt/media/ssdt-procwithencryption.gif "Скрипт с фиктивным текстом")  
  
Если доступно и может быть получено полное определение объекта, операция импорта или сравнения схемы поместит его в проект полностью. Это происходит при обновлении проекта из скрипта, файла DACPAC, построенного на основе проекта базы данных, или другого проекта базы данных.  
  
