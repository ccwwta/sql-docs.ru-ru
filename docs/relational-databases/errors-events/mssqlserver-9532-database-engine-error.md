---
description: MSSQLSERVER_9532
title: MSSQLSERVER_ 9532 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 9532 (Database Engine error)
ms.assetid: ab95cce8-4f97-4aea-a746-a73eea7c9aab
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1bd1948e2475b792198465ed8befc838ab00db48
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99187570"
---
# <a name="mssqlserver_9532"></a>MSSQLSERVER_9532
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|9532|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|XMLERR_COLUMNSET_CANNOT_CONVERT_FROM_TO|  
|Текст сообщения|При обработке запроса или операции DML над набором столбцов "%.*ls" произошла ошибка преобразования данных типа "%ls" к типу "%ls" для столбца "%.\*ls".|  
  
## <a name="explanation"></a>Объяснение  
Набор столбцов представляет собой нетипизированное XML-представление, объединяющее несколько столбцов таблицы в виде структурированного вывода. При вставке или обновлении значений разреженного столбца в наборе XML-столбцов значения, вставляемые в базовые разреженные столбцы, неявным образом преобразуются из типа данных **xml**. Было передано значение, которое не может быть преобразовано в тип данных столбца.  
  
## <a name="user-action"></a>Действие пользователя  
Поскольку предоставленное значение не удалось неявно преобразовать, запись может оказаться недопустимой. Исправьте ошибку и повторите попытку. Если значение является верным, измените инструкцию таким образом, чтобы использовались отдельные столбцы, а не набор столбцов. Это позволит выполнить приведение значения в правильный тип данных явным образом.  
  
