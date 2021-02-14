---
description: Создание коллекции (службы Master Data Services)
title: Создание коллекции
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating collections [Master Data Services]
- collections [Master Data Services], creating
ms.assetid: 3d4f152c-863c-4385-bca9-a9fcd0402e1f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d33d856cae301c8c30efe6a6edda12f676b90bb7
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100272715"
---
# <a name="create-a-collection-master-data-services"></a>Создание коллекции (службы Master Data Services)

[!INCLUDE [SQL Server - Windows only ASDBMI  ](../includes/applies-to-version/sql-windows-only-asdbmi.md)]

  Если нужно создать плоские списки конечных и консолидированных элементов, создайте коллекцию в среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]. Коллекции необязательно должны включать все элементы из сущности.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения этой процедуры:  
  
-   Необходимо иметь разрешение на доступ к функциональной области **Обозреватель** .  
  
-   как минимум необходимо разрешение **Обновление** на объект модели коллекции для сущности;  
  
### <a name="to-create-a-collection"></a>Создание коллекции  
  
1.  На домашней странице [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] выберите модель в списке **Модель** .  
  
2.  Выберите версию из списка **Версия** .  
  
3.  Нажмите кнопку **Браузер**.  
  
4.  В строке меню наведите указатель на меню **Коллекции** и выберите пункт *entity_name*.  
  
5.  Нажмите кнопку **Добавить коллекцию**.  
  
6.  На вкладке **Подробные сведения** в поле **Имя** введите имя коллекции.  
  
7.  В поле **Код** введите уникальный код коллекции.  
  
8.  При необходимости в текстовом поле **Описание** введите описание коллекции.  
  
9. Нажмите кнопку **ОК**.  
  
## <a name="next-steps"></a>Next Steps  
  
-   [Добавление элементов в коллекцию (службы Master Data Services)](../master-data-services/add-members-to-a-collection-master-data-services.md)  
  
## <a name="see-also"></a>См. также:  
 [&#40;коллекций Master Data Services&#41;](../master-data-services/collections-master-data-services.md)   
 [Удаление элемента или коллекции &#40;Master Data Services&#41;](../master-data-services/delete-a-member-or-collection-master-data-services.md)   
 [Создание явной иерархии (службы Master Data Services)](../master-data-services/create-an-explicit-hierarchy-master-data-services.md)  
  
  
