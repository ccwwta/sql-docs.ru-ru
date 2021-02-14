---
title: выполнить частичный запрос
description: Узнайте, как отлаживать разделы сложных запросов. Используйте редактор Transact-SQL для выделения определенного фрагмента скрипта и выполнения его как отдельного запроса.
ms.prod: sql
ms.technology: ssdt
ms.topic: conceptual
ms.assetid: af04ab37-6cbb-4185-9382-e5922fa5b1df
author: markingmyname
ms.author: maghan
ms.reviewer: “”
ms.custom: seo-lt-2019
ms.date: 02/09/2017
ms.openlocfilehash: 25ad063fc90539647a48bac2702e0cd2b80cd53b
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100018204"
---
# <a name="how-to-execute-a-partial-query"></a>Руководство. выполнить частичный запрос

Редактор Transact\-SQL позволяет выделять определенный фрагмент скрипта и выполнять его как отдельный запрос. Это упрощает отладку фрагментов сложных запросов.  
  
> [!WARNING]  
> В следующих процедурах используются сущности, которые созданы в рамках процедур, описанных в руководствах по [разработке подключенной базы данных](../ssdt/connected-database-development.md) и [автономной разработке базы данных с учетом проекта](../ssdt/project-oriented-offline-database-development.md).  
  
## <a name="to-partially-execute-a-query"></a>Частичное выполнение запроса  
  
1. В **обозревателе объектов SQL Server** дважды щелкните представление **PerishableFruits** в разделе **Представления**, чтобы открыть его в редакторе Transact\-SQL.  
  
2. Выделите сегмент `SELECT p.Id, p.Name FROM dbo.Product p` в коде, щелкните правой кнопкой мыши и выберите **Выполнить запрос**.  
  
3. Обратите внимание, что все строки с указанными полями в таблице `Products` возвращаются в области **Результаты**.