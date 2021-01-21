---
title: Сбор данных в элементе управления ReportViewer
description: ReportViewer собирает анонимные данные об использовании, чтобы понять, как клиенты используют продукт, и позволяет сосредоточиться на улучшениях, наиболее важных для клиентов.
author: maggiesMSFT
ms.author: maggies
ms.custom: seo-lt-2019
ms.reviewer: ''
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: application-integration
ms.topic: reference
ms.date: 06/03/2020
ms.openlocfilehash: 685b1004cea15c5e1c1708204e75b9c8ce7a40af
ms.sourcegitcommit: d8cdbb719916805037a9167ac4e964abb89c3909
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/20/2021
ms.locfileid: "98596576"
---
# <a name="integrate-reporting-services-using-reportviewer-controls---data-collection"></a>Интеграция служб Reporting Services с помощью элементов управления ReportViewer — сбор данных

Элемент управления собирает анонимные данные, которые позволяют лучше понять, как клиенты используют продукт. Данные об использовании позволяют улучшать продукт в будущем.

Описание методик сбора и использования данных Microsoft SQL Server и средства просмотра отчетов приведено в [заявлении о конфиденциальности](../../sql-server/sql-server-privacy.md).

## <a name="opting-out-of-data-collection"></a>Отказ от сбора данных

Сбор данных об использовании можно отключить с помощью свойства ```EnableTelemetry```.

```xml
<rsweb:ReportViewer ID="ReportViewer1" runat="server" EnableTelemetry="false">
</rsweb:ReportViewer>
```

Кроме того, это можно сделать программным способом перед настройкой элемента управления.
    
```csharp
protected void Page_Load(object sender, EventArgs e)
{
    ReportViewer1.EnableTelemetry = false;
}
```
## <a name="see-also"></a>См. также раздел

[Using the WebForms ReportViewer Control](../../reporting-services/application-integration/using-the-webforms-reportviewer-control.md) (Использование элемента управления средства просмотра отчетов WebForms)  
[Интеграция служб Reporting Services с помощью элементов управления средства просмотра отчетов](../../reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls.md)