---
description: Назначение флага версии (службы Master Data Services)
title: Назначение флага версии
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- version flags [Master Data Services], assigning flags
- versions [Master Data Services], assigning flags
ms.assetid: 6629ec7e-32e7-4a1e-8b31-eb43c5923766
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: afae8607f55b437071c4b04789c595d9c096f722
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100339510"
---
# <a name="assign-a-flag-to-a-version-master-data-services"></a>Назначение флага версии (службы Master Data Services)

[!INCLUDE [SQL Server - Windows only ASDBMI  ](../includes/applies-to-version/sql-windows-only-asdbmi.md)]

  В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]назначается флаг версии, чтобы указать версию, которую следует использовать пользователям или системам-подписчикам.  
  
> [!NOTE]  
>  Флаг можно назначить только одной версии в каждый момент времени. Если назначить флаг, уже назначенный другой версии, то он переместится к выбранной версии.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения этой процедуры:  
  
-   необходимо иметь разрешение на доступ к функциональной области **Управление версиями** ;  
  
-   необходимо быть администратором модели. Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
-   Нужно создать флаг версии для назначения. Дополнительные сведения см. в статье [Создание флага версии (службы Master Data Services)](../master-data-services/create-a-version-flag-master-data-services.md).  
  
-   Необходимо иметь разрешение на доступ к функциональной области "Управление версиями". Дополнительные сведения см. в разделе [разрешения функциональной области &#40;Master Data Services&#41;](../master-data-services/functional-area-permissions-master-data-services.md).  
  
### <a name="to-assign-a-flag-to-a-version"></a>Назначение флага версии  
  
1.  В среде [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Управление версиями**.  
  
2.  На странице **Управление версиями** в строке версии, которой необходимо назначить флаг, дважды щелкните ячейку в столбце **Флаг** .  
  
3.  Выберите из списка флаг, который нужно назначить.  
  
    > [!NOTE]  
    >  Если нужный флаг недоступен, то, возможно, он доступен только для **зафиксированных** версий. Чтобы удостовериться в этом, перейдите на страницу **Управление флагами версии** и просмотрите поле **Только зафиксированные версии** флага.  
  
4.  Нажмите клавишу ВВОД, чтобы сохранить изменение.  
  
## <a name="see-also"></a>См. также:  
 [Создание флага версии &#40;Master Data Services&#41;](../master-data-services/create-a-version-flag-master-data-services.md)   
 [Версии (службы Master Data Services)](../master-data-services/versions-master-data-services.md)  
  
  
