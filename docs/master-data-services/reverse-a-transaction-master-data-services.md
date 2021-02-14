---
description: Отмена транзакции (службы Master Data Services)
title: Отмена транзакции
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Master Data Services], reversing
ms.assetid: 6f7c3f07-0f64-4283-8c9c-93facd00a046
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 72598e6b0dd5c86cb5f231c4ac01ffd1d499b98b
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100340245"
---
# <a name="reverse-a-transaction-master-data-services"></a>Отмена транзакции (службы Master Data Services)

[!INCLUDE [SQL Server - Windows only ASDBMI  ](../includes/applies-to-version/sql-windows-only-asdbmi.md)]

  В службах [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]администратор может обратить транзакцию, когда необходимо отменить действие. Примеры транзакций: изменения значений атрибутов, перемещение иерархий, удаление элементов. Этот раздел относится только к транзакциям сущностей с типом журнала транзакций "Атрибут". Перейдите на страницу обозревателя сущностей для просмотра журнала сущностей с типом журнала транзакций "Элемент".  
  
## <a name="prerequisites"></a>Предварительные требования  
  
-   необходимо иметь разрешение на доступ к функциональной области **Управление версиями** ;  
  
-   необходимо быть администратором модели. Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
### <a name="to-reverse-a-transaction"></a>Отмена транзакции  
  
1.  На домашней странице [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] нажмите **Управление версиями**.  
  
2.  В строке меню выберите пункт **Транзакции**.  
  
3.  На странице **Транзакции** выберите модель в списке **Модель** .  
  
4.  Выберите версию из списка **Версия** .  
  
5.  Щелкните в сетке строку транзакции, которую необходимо отменить.  
  
6.  Нажмите кнопку **Отменить транзакцию**.  
  
7.  В диалоговом окне подтверждения нажмите кнопку **ОК**. В сетку добавляется еще одна транзакция, соответствующая отмененной транзакции.  
  
## <a name="see-also"></a>См. также:  
 [Master Data Services &#40;транзакций&#41;](../master-data-services/transactions-master-data-services.md)   
 [Повторная активация элемента или коллекции (службы Master Data Services)](../master-data-services/reactivate-a-member-or-collection-master-data-services.md)  
 [Откат журнала изменений элемента](../master-data-services/rollback-member-revision-history-master-data-services.md)
  
  
