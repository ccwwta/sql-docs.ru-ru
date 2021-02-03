---
description: MSSQLSERVER_107
title: MSSQLSERVER_107 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 107 (Database Engine error)
ms.assetid: f33f514c-56aa-42e2-841b-e91244da90e2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dcd1043ccfd56b03b13731a8a2b0b2772bf13163
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99197325"
---
# <a name="mssqlserver_107"></a>MSSQLSERVER_107
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|107|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|P_NOCORRMATCH|  
|Текст сообщения|Префикс столбца «%.*ls» не совпадает с именем таблицы или псевдонимом, используемым в запросе.|  
  
## <a name="explanation"></a>Объяснение  
Список выбора запроса содержит звездочку (*), которая неправильно дополнена префиксом столбца. Эта ошибка может быть возвращена при следующих условиях.  
  
-   Префикс столбца не соответствует ни одному имени таблицы или псевдониму, используемому в запросе. Например, в следующей инструкции в качестве префикса столбца используется псевдоним (`T1`), но этот псевдоним не определен в предложении FROM.  
  
    ```  
    SELECT T1.* FROM dbo.ErrorLog;  
    ```  
  
-   В качестве префикса столбца указано имя таблицы, а в предложении FROM для таблицы указан псевдоним. Например, в следующей инструкции в качестве префикса столбца используется имя таблицы `ErrorLog`, но таблица имеет псевдоним (`T1`), определенный в предложении FROM.  
  
    ```  
    SELECT ErrorLog.* FROM dbo.ErrorLog AS T1;  
    ```  
  
    Если в предложении FROM предусмотрен псевдоним для имени таблицы, то для обозначения префиксом столбцов этой таблицы можно использовать только псевдоним.  
  
## <a name="user-action"></a>Действие пользователя  
Префиксы столбцов должны быть согласованы с именами таблиц или псевдонимами, указанными в предложении FROM запроса. Например, приведенные выше инструкции могут быть исправлены следующим образом:  
  
```  
SELECT T1.* FROM dbo.ErrorLog AS T1;  
```  
  
или диспетчер конфигурации служб  
  
```  
SELECT ErrorLog.* FROM dbo.ErrorLog;  
```  
  
## <a name="see-also"></a>См. также:  
[MSSQLSERVER_4104](~/relational-databases/errors-events/mssqlserver-4104-database-engine-error.md)  
  
