---
description: Data Quality Services
title: Data Quality Services
ms.date: 10/12/2013
ms.prod: sql
ms.prod_service: data-quality-services
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 9c6b996c-e768-4bf5-837f-5436ed9cea1d
author: swinarko
ms.author: sawinark
ms.openlocfilehash: 12e37d3119341ebef2c3592581fd0fada018210e
ms.sourcegitcommit: 108bc8e576a116b261c1cc8e4f55d0e0713d402c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2021
ms.locfileid: "98765811"
---
# <a name="data-quality-services"></a>Data Quality Services

[!INCLUDE [SQL Server - Windows only ASDBMI  ](../includes/applies-to-version/sqlserver.md)]

[!INCLUDE[ssDQSnoversionLong](../includes/ssdqsnoversionlong-md.md)] (DQS) — это продукт, предназначенный для повышения качества данных на основе знаний. DQS позволяет построить базу знаний и использовать ее для выполнения разнообразных важных задач по обеспечению качества данных, включая исправление, дополнение, стандартизацию и устранение дубликатов данных. DQS позволяет выполнять очистку данных с использованием служб эталонных данных, расположенных в облаке и предоставляемых поставщиками эталонных данных. DQS также предоставляет функции профилирования, встроенные в задачи по обеспечению качества данных, что позволяет анализировать целостность данных.  
  
 DQS состоит из [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] и [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], которые устанавливаются в составе [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)]. [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] — это компонент экземпляра SQL Server, состоящий из трех каталогов SQL Server с функциями обеспечения качества данных и хранения. [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] — это общий компонент SQL Server, который используется бизнес-пользователями, информационными работниками и ИТ-специалистами для выполнения автоматизированного анализа качества данных и интерактивного управления качеством данных. Также вы можете выполнять процессы обеспечения качества данных с помощью функций, доступных в [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)] и службах Master Data Services (MDS), которые основаны на DQS.  
  
 Подробные сведения об установке DQS см. в разделе [Install Data Quality Services](../data-quality-services/install-windows/install-data-quality-services.md). Если вы хотите обновить существующую версию служб DQS до последней версии [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] , см. статью [Обновление служб Data Quality Services](../database-engine/install-windows/upgrade-data-quality-services.md).  
  
 **Просмотр содержимого по областям**  
 ![Маленький значок папки с файлами](/analysis-services/analysis-services/media/filefolder-small.png "Маленький значок папки") [Data Quality Client приложение](../data-quality-services/data-quality-client-application.md)  
  
 ![Маленький значок папки](/analysis-services/analysis-services/media/filefolder-small.png "Маленький значок папки") [базы знаний и домены DQS](../data-quality-services/dqs-knowledge-bases-and-domains.md)  
  
 ![Маленький значок папки с файлами](/analysis-services/analysis-services/media/filefolder-small.png "Маленький значок папки") [проекты качества данных](../data-quality-services/data-quality-projects-dqs.md)  
  
 ![Маленький значок папки](/analysis-services/analysis-services/media/filefolder-small.png "Маленький значок папки") [Очистка данных](../data-quality-services/data-cleansing.md)  
  
 ![Маленький значок папки с файлами](/analysis-services/analysis-services/media/filefolder-small.png "Маленький значок папки") [сопоставление данных](../data-quality-services/data-matching.md)  
  
 ![Маленький значок папки](/analysis-services/analysis-services/media/filefolder-small.png "Маленький значок папки") со [ссылками службы данных в DQS](../data-quality-services/reference-data-services-in-dqs.md)  
  
 ![Маленький значок папки с файлами](/analysis-services/analysis-services/media/filefolder-small.png "Маленький значок папки") [Профилирование данных и уведомления в DQS](../data-quality-services/data-profiling-and-notifications-in-dqs.md)  
  
 ![Маленький значок папки](/analysis-services/analysis-services/media/filefolder-small.png "Маленький значок папки") [Администрирование DQS](../data-quality-services/dqs-administration.md)  
  
 ![Маленький значок папки](/analysis-services/analysis-services/media/filefolder-small.png "Маленький значок папки") [Безопасность DQS](../data-quality-services/dqs-security.md)  
  
## <a name="see-also"></a>См. также:  
 [Общие сведения о службах Data Quality Services](../data-quality-services/introduction-to-data-quality-services.md)   
 [Основные понятия служб Data Quality Services](../data-quality-services/data-quality-services-concepts.md)   
 [Ресурсы DQS](../sql-server/index.yml)   
 [Центр ресурсов SQL Server](/previous-versions/sql/sql-server-2012/hh231622(v=sql.110))  
  
