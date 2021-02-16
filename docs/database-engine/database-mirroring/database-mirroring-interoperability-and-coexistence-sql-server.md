---
title: Зеркальное отображение базы данных. Взаимодействие и совместная работа
description: Узнайте о взаимодействии и сосуществовании зеркального отображения базы данных SQL Server и других компонентов SQL Server, таких как полнотекстовые каталоги и моментальные снимки базы данных.
ms.custom: seo-lt-2019
ms.date: 05/17/2016
ms.prod: sql
ms.prod_service: high-availability
ms.reviewer: ''
ms.technology: database-mirroring
ms.topic: conceptual
helpviewer_keywords:
- high availability [SQL Server], interoperability and coexistence
- Database Engine [SQL Server], high availability
ms.assetid: 89fef397-e0cf-4e08-b598-25b8d4170523
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5bd20c8ef36e676ab02430bc0da9d44f2de34768
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100353163"
---
# <a name="database-mirroring-interoperability-and-coexistence-sql-server"></a>Зеркальное отображение базы данных. Взаимодействие и сосуществование (SQL Server)
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  Зеркальное отображение базы данных можно использовать со следующими возможностями и компонентами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:  
  
-   [Экземпляры отказоустойчивой кластеризации AlwaysOn (отказоустойчивый кластер SQL Server)](../../database-engine/database-mirroring/database-mirroring-and-sql-server-failover-cluster-instances.md)  
  
-   [Отслеживание измененных данных (и отслеживание изменений)](../../relational-databases/track-changes/change-data-capture-and-other-sql-server-features.md)  
  
-   [Моментальные снимки базы данных](../../database-engine/database-mirroring/database-mirroring-and-database-snapshots-sql-server.md)  
  
-   [Полнотекстовые каталоги](../../database-engine/database-mirroring/database-mirroring-and-full-text-catalogs-sql-server.md)  
  
-   [Доставка журналов](../../database-engine/database-mirroring/database-mirroring-and-log-shipping-sql-server.md)  
  
-   [Репликация](../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md)  
  
 Зеркальное отображение базы данных не работает совместно со следующими функциями.  
  
-   Транзакции между разными базами данных или распределенные транзакции  
  
     Сведения о том, почему не поддерживаются такие транзакции, см. в разделе [Транзакции между базами данных и распределенные транзакции для групп доступности AlwaysOn и зеркального отображения базы данных (SQL Server)](../../database-engine/availability-groups/windows/transactions-always-on-availability-and-database-mirroring.md).  
  
-   [!INCLUDE[ssHADR](../../includes/sshadr-md.md)]  
  
## <a name="see-also"></a>См. также:  
 [Зеркальное отображение базы данных (SQL Server)](../../database-engine/database-mirroring/database-mirroring-sql-server.md)  
  
  
