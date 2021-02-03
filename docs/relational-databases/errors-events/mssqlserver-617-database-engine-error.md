---
description: MSSQLSERVER_617
title: MSSQLSERVER_617 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 617 (Database Engine error)
ms.assetid: 213545d9-08a7-4427-bfd1-8b7e16644281
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b8e13fc075beacb1e592e265088bbc894ca5cf2c
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99190692"
---
# <a name="mssqlserver_617"></a>MSSQLSERVER_617
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|617|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|NODESHASH|  
|Текст сообщения|Дескриптор объекта с идентификатором %ld в базе данных с идентификатором %d не обнаружен в хэш-таблице при попытке его восстановления по хэшу. В рабочей таблице отсутствует запись. Повторите запрос. Если используется курсор, закройте и заново откройте его.|  
  
## <a name="explanation"></a>Объяснение  
SQL Server не может найти рабочую таблицу для конкретной записи.  
  
## <a name="user-action"></a>Действие пользователя  
  
1.  Если используется курсор, закройте и заново откройте его.  
  
2.  Повторите запрос.  
  
