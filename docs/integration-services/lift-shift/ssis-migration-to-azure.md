---
title: Обзор миграции SQL Server Integration Services в Azure | Документация Майкрософт
description: Эта статья описывает процедуру и средства для миграции SQL Server Integration Services в Azure.
ms.date: 04/10/2020
ms.topic: conceptual
ms.prod: sql
ms.prod_service: integration-services
ms.custom: ''
ms.technology: integration-services
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f443bc4209365253cf6e4e4005d19afe9ee11268
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100061469"
---
# <a name="migrate-on-premises-ssis-workloads-to-ssis-in-adf"></a>Миграция локальных рабочих нагрузок служб SSIS в службы SSIS в ADF

Эта статья описывает процедуру и средства, помогающие перенести рабочие нагрузки SQL Server Integration Services (SSIS) в службы SSIS в ADF.

[Общие сведения о миграции](/azure/data-factory/scenario-ssis-migration-overview) описывают общий процесс миграции рабочих нагрузок извлечения, преобразования и загрузки из локальных служб SSIS в службы SSIS в ADF.

Процесс миграции состоит из двух этапов: [оценка](/azure/data-factory/scenario-ssis-migration-overview#assessment) и [миграция](/azure/data-factory/scenario-ssis-migration-overview#migration).

## <a name="assessment"></a>Оценка

Помощник по миграции данных (DMA) представляет собой бесплатное скачиваемое средство для этой цели, которое можно установить и запустить локально. Можно создать проект оценки DMA типа Integration Services, чтобы оценить пакеты SSIS в пакетах и определить проблемы совместимости.

Получите [помощник по миграции баз данных](../../dma/dma-overview.md) и [выполните оценку пакетов](../../dma/dma-assess-ssis.md).

## <a name="migration"></a>Миграция

В зависимости от типов хранилища исходных пакетов SSIS и назначения миграции рабочих нагрузок базы данных шаги по переносу пакетов SSIS и заданий агента SQL Server, планирующих выполнение пакетов служб SSIS, могут отличаться. Дополнительные сведения см. [на этой странице](/azure/data-factory/scenario-ssis-migration-overview#migration).

## <a name="next-steps"></a>Дальнейшие действия

- [Перенос пакетов Integration Services в Управляемый экземпляр SQL Azure](/azure/dms/how-to-migrate-ssis-packages-managed-instance).
- [Перенос заданий SSIS в Фабрику данных Azure (ADF) с помощью SQL Server Management Studio (SSMS)](/azure/data-factory/how-to-migrate-ssis-job-ssms).