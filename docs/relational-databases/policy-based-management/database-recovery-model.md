---
title: Модель восстановления базы данных
description: Узнайте, как включить политику для проверки модели восстановления резервной копии для пользовательских баз данных, чтобы снизить потери данных.
ms.custom: seo-lt-2019
ms.date: 08/31/2020
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
author: dzsquared
ms.author: drskwier
ms.openlocfilehash: 8c68b60243ec033fff3735901cc4e35134222704
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100345507"
---
# <a name="database-recovery-model"></a>Модель восстановления базы данных
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  В выпусках SQL Server Enterprise и Standard это правило проверяет наличие пользовательских баз данных с возможностью записи и простой моделью восстановления. Для производственных баз данных рекомендуется использовать модель полного восстановления вместо простой. Режим полного восстановления делает возможным восстановление данных на момент времени. Это позволяет снизить потери данных при аварийном восстановлении.
  
## <a name="best-practices-recommendations"></a>Рекомендации  
 Чтобы обеспечить возможность восстановления с минимальной потерей данных, для производственных баз данных следует применять режим полного восстановления и запланировать частое создание резервных копий журнала транзакций.
  
## <a name="see-also"></a>См. также раздел 
  
 [Обзор процессов восстановления](../backup-restore/restore-and-recovery-overview-sql-server.md)   
  
 [Выполнение полного восстановления базы данных (модель полного восстановления)](../backup-restore/complete-database-restores-full-recovery-model.md)  

 [Резервные копии журналов транзакций](../backup-restore/transaction-log-backups-sql-server.md)   
  
