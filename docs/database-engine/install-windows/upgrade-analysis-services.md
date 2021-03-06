---
description: Обновление служб Analysis Services
title: Обновление служб Analysis Services | Документы Майкрософт
ms.custom: ''
ms.date: 12/09/2020
ms.prod: sql
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- upgrading databases
- databases [Analysis Services], upgrading
- installing Analysis Services, side-by-side installations
- Analysis Services upgrades
- Analysis Services upgrades, about upgrading Analysis Services
- SSAS, database migration
- upgrading Analysis Services
- installing Analysis Services, upgrading
- SSAS, upgrading
ms.assetid: a131d329-386e-4470-aaa9-ffcde4e5ec0c
author: Minewiskan
ms.author: owend
monikerRange: '>=sql-server-2016'
manager: erikre
ms.openlocfilehash: 73258d31f23c52915319aa765dd8d9bcbb7f2e35
ms.sourcegitcommit: 1a544cf4dd2720b124c3697d1e62ae7741db757c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2020
ms.locfileid: "97480355"
---
# <a name="upgrade-analysis-services"></a>Обновление служб Analysis Services

[!INCLUDE [SQL Server -Windows Only](../../includes/applies-to-version/sql-windows-only.md)]
  
  Чтобы воспользоваться преимуществами функций, появившихся в текущем выпуске, вы можете перевести экземпляры служб Analysis Services на версию SQL Server с аналогичным режимом сервера. Эта процедура описана в разделе [Новые возможности в службах Analysis Services](/analysis-services/what-s-new-in-analysis-services).  
  
 Вы можете обновить каждый экземпляр на месте независимо от других экземпляров, выполняемых на том же оборудовании. Но большинство администраторов устанавливают экземпляр новой версии для тестирования приложений, прежде чем переносить рабочие нагрузки на новый сервер. Однако для серверов разработки или тестирования обновление на месте может быть более удобным.  
  
## <a name="server-upgrade"></a>Обновление сервера  
 Существует два основных подхода к обновлению серверов и баз данных:  
  
> [!NOTE]
> Уровни совместимости баз данных, подключенных к данному серверу, остаются прежними, если вы не изменили их вручную.
   
  
### <a name="in-place-upgrade"></a>Обновление «на месте»  
 Обновление автоматически переносит существующие базы данных из старого экземпляра в новый. Поскольку метаданные и двоичные данные между двумя версиями совместимы, после обновления данные сохраняются и их не нужно переносить вручную.  
  
 Чтобы обновить существующий экземпляр, запустите программу установки и укажите имя существующего экземпляра в качестве имени нового экземпляра.  
  
### <a name="side-by-side-upgrade"></a>Параллельное обновление  
  
-   Создайте резервные копии для всех баз данных и убедитесь, что каждая из них может быть восстановлена. Дополнительные сведения см. в разделе [Резервное копирование и восстановление баз данных Analysis Services](/analysis-services/multidimensional-models/backup-and-restore-of-analysis-services-databases).  
  
-   Определите подмножество отчетов, электронных таблиц или моментальных снимков панелей мониторинга для последующего использования в качестве основы для подтверждения операций, выполняемых после обновления сервера. Если это возможно, соберите показатели производительности, чтобы провести сравнение показателей для тех же рабочих нагрузок на обновленном сервере.  
  
-   Установите новый экземпляр служб Analysis Services, выбрав тот же режим сервера (табличный или многомерный), что используется на сервере, который требуется заменить. 
  
     Выполните действия после установки для настройки портов и добавления администраторов сервера. Дополнительные сведения см. в статье [Настройка после установки &#40;службы Analysis Services&#41;](/analysis-services/instances/post-install-configuration-analysis-services).  
  
-   Подключите или восстановите каждую базу данных.  
  
-   Запустите DBCC для проверки целостности базы данных. Табличные модели подвергаются более тщательной проверке с поиском потерянных объектов в иерархии модели. Для многомерных моделей проверяются только индексы секций. Дополнительные сведения см. в статье [Средство проверки согласованности базы данных &#40;DBCC&#41; для табличных и многомерных баз данных Analysis Services](/analysis-services/instances/database-consistency-checker-dbcc-for-analysis-services).  
  
-   Проверьте отчеты, электронные таблицы и панели мониторинга, чтобы убедиться, что в поведении и вычислениях нет нежелательных изменений. Производительность многомерных и табличных рабочих нагрузок должна повыситься.  
  
-   Протестируйте операции обработки, при необходимости устраните ошибки со входом в систему и разрешениями. При использовании для подключения учетной записи службы по умолчанию новая служба будет запущена под другой учетной записью. Дополнительные сведения см. в разделе [Настройка учетных записей служб &#40;Analysis Services&#41;](/analysis-services/instances/configure-service-accounts-analysis-services).  
  
-   Протестируйте операции резервного копирования и восстановления на обновленном сервере, указав в сценариях новое имя сервера.  
  
## <a name="database-upgrade"></a>Обновление базы данных  
 Базы данных, созданные в предыдущих версиях, работают на обновленном сервере с исходным значением уровня совместимости. Как правило, базу данных или модель можно обновить для работы на более высоком уровне совместимости, чтобы получить доступ к новым возможностям, но имейте в виду, что это привязывает вас к конкретной версии сервера.  
  
 Для обновления базы данных вы обычно обновляете модель в SQL Server Data Tools (SSDT), а затем развертываете решение в экземпляре обновленного сервера.
  
 В табличных и многомерных базах данных используются различные пути к версиям. То, что числа уровней совместимости для многомерных и табличных моделей похожи — случайность.  Если изменение функции влияет только на один режим, режимы будут изменяться с различной скоростью.  
  
 Для образовательных целей в следующей таблице перечислены уровни совместимости, но для понимания возможностей каждого уровня нужно изучить соответствующую статью.  
  
|Модель базы данных|Уровень совместимости|Совместимые версии|  
|-|-|-|  
|Таблица|1500|SQL Server 2019|
|Таблица|1400|SQL Server 2017|
|Таблица|1200|SQL Server 2016|  
|Таблица|1103|SQL Server 2014|  
|Таблица|1100|SQL Server 2012|  
|Многомерная|1100|SQL Server 2012 и более поздней версии|  
|Многомерная|1050|SQL Server 2005, 2008, 2008 R2|  
  
 Дополнительные сведения см. в статьях [Уровень совместимости многомерной базы данных &#40;службы Analysis Services&#41;](/analysis-services/multidimensional-models/compatibility-level-of-a-multidimensional-database-analysis-services) и [Уровень совместимости табличных моделей служб Analysis Services](/analysis-services/tabular-models/compatibility-level-for-tabular-models-in-analysis-services).  
  
## <a name="see-also"></a>См. также раздел  
 [Планирование установки SQL Server](../../sql-server/install/planning-a-sql-server-installation.md)   
 [Обновление Power Pivot для SharePoint](../../database-engine/install-windows/upgrade-power-pivot-for-sharepoint.md)   
  
