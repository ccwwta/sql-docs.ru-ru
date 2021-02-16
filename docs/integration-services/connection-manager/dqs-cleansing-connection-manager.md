---
description: Диспетчер соединений «Очистка DQS»
title: Диспетчер подключений "Очистка DQS" | Документы Майкрософт
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: faa1eedd-db14-41e5-8e58-8f0f6f561e42
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dc0bb9e5238e490689b9ffa57836d2db0666e75b
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100338431"
---
# <a name="dqs-cleansing-connection-manager"></a>Диспетчер соединений «Очистка DQS»

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  Диспетчер соединений «Очистка DQS» позволяет пакету подключаться к серверу служб [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] . Преобразование «Очистка DQS» использует диспетчер соединений «Очистка DQS».  
  
 Дополнительные сведения о службах Data Quality Services см. в разделе [Data Quality Services Concepts](../../data-quality-services/data-quality-services-concepts.md).  
  
> [!IMPORTANT]  
>  Диспетчер соединений «Очистка DQS» поддерживает только проверку подлинности Windows.  
  
## <a name="related-tasks"></a>Связанные задачи  
 Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами. Дополнительные сведения о свойствах, которые можно установить в конструкторе [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в статье [Диалоговое окно редактора преобразования "Очистка DQS"](../data-flow/transformations/dqs-cleansing-transformation.md).  
  
 Дополнительные сведения о настройке диспетчера подключений программным образом см. в документации по классу <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> в руководстве для разработчиков.  
  
