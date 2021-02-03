---
description: MSSQLSERVER_21862
title: MSSQLSERVER_21862 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 21862 (Database Engine error)
ms.assetid: a1d393dd-453b-4d45-9aa5-7d371213e32b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9e722121773db00eb1411b42a0206d83a22484c4
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99196393"
---
# <a name="mssqlserver_21862"></a>MSSQLSERVER_21862
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|MSSQLSERVER|  
|Идентификатор события|21862|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|SQLErrorNum21862|  
|Текст сообщения|Столбцы FILESTREAM нельзя опубликовать в публикации с использованием метода синхронизации «database snapshot» или «database snapshot character».|  
  
## <a name="explanation"></a>Объяснение  
Данные FILESTREAM недоступны через моментальный снимок базы данных, поэтому агент моментальных снимков не сможет прочитать данные FILESTREAM, если в качестве метода синхронизации публикации указан параметр *database snapshot* или *database_snapshot_character*.  
  
## <a name="user-action"></a>Действие пользователя  
Измените метод синхронизации публикации на любой другой, кроме *database snapshot* или *database_snapshot_character*, либо просто исключите столбец FILESTREAM из публикации.  
  
