---
description: Расширенный выбор объектов (MySQLToSQL)
title: Расширенный выбор объектов (MySQLToSQL) | Документация Майкрософт
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 390ef0c2-107c-4443-9495-80f35f22d168
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: 04cd57eed572a35d2810a9812f5701974f4f14a4
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100069229"
---
# <a name="advanced-object-selection--mysqltosql"></a>Расширенный выбор объектов (MySQLToSQL)
Диалоговое окно " **Расширенный раздел объекта** " позволяет фильтровать объекты базы данных с помощью строк и подстрок в имени объекта, а затем выбирать или отменять выбор этих объектов. SSMA выполняет операции преобразования и миграции для выбранных объектов.  
  
Чтобы открыть это диалоговое окно, щелкните правой кнопкой мыши в обозревателе метаданных и выберите **Расширенный выбор объектов**.  
  
При первом открытии диалогового окна нажмите кнопку **Показать элементы подкатегорий** , чтобы отобразить все объекты, метаданные которых загружены в проект. Затем можно ввести строки для фильтрации элементов. Например, введите строку "Company", чтобы отобразить все элементы с именами, включающими эту строку.  
  
Перед использованием этого диалогового окна может потребоваться принудительно загрузить все метаданные с помощью SSMA, либо путем преобразования схем, либо путем сохранения проекта.  
  
## <a name="options"></a>Параметры  
**Проверить все элементы**  
Добавляет галочку рядом со всеми элементами. Эти элементы будут сразу же выбраны в обозревателе метаданных.  
  
**Снять флажки для всех элементов**  
Снимает флажок рядом со всеми элементами. Эти элементы будут немедленно удалены в обозревателе метаданных.  
  
**Режим просмотра списка**  
Отображает отфильтрованные элементы в списке.  
  
**Режим представления таблицы**  
Отображает отфильтрованные элементы в таблице.  
  
**Отображаются только загруженные элементы**  
Переключает отображение категорий или элементов. Если эта кнопка выбрана, SSMA отображает все элементы, соответствующие условиям фильтра, и ранее загруженные. Если эта кнопка не выбрана, SSMA отображает папки категорий.  
  
**Фильтр**  
Введите строку, которая будет использоваться для фильтрации элементов. Например, чтобы найти все доступные элементы, содержащие строку "ID" в имени элемента, введите строку "ID" в поле **фильтра** .  
  
Если элементы соответствуют условиям фильтра, то категории или элементы будут отображаться при вводе строки. Чтобы просмотреть соответствующие элементы, рекомендуется нажать кнопку **отображаемые только загруженные элементы** .  
  
**Очистить фильтр**  
Очищает поле **фильтра** .  
  
