---
description: Скрыть системные объекты в обозревателе объектов
title: Скрыть системные объекты в обозревателе объектов
ms.custom: seo-lt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- hiding system objects
- system objects [SQL Server]
- objects [SQL Server], hiding
- Object Explorer, hiding objects
ms.assetid: c01d8804-838c-4f75-b78c-80e41e4fffdc
author: markingmyname
ms.author: maghan
ms.openlocfilehash: dc993e993f3a1ac63dda6e9dd3fd36d31f6a0316
ms.sourcegitcommit: 38e055eda82d293bf5fe9db14549666cf0d0f3c0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2021
ms.locfileid: "99250542"
---
# <a name="hide-system-objects-in-object-explorer"></a>Скрыть системные объекты в обозревателе объектов
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]
В этом разделе описывается, как скрыть системные объекты в обозревателе объектов [!INCLUDE[ssnoversion](../../includes/ssnoversion-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]. Узел **Базы данных** в обозревателе объектов содержит системные объекты, такие как системные базы данных. На страницах **Сервис**/**Параметры** можно скрыть системные объекты. На некоторые системные объекты, например системные функции и типы данных, эта настройка не влияет.  
  
## <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a>Использование среды SQL Server Management Studio  
  
#### <a name="to-hide-system-objects-in-object-explorer"></a>Скрытие системных объектов в обозревателе объектов  
  
1.  В меню **Сервис** выберите команду **Параметры**.  
  
2.  На странице **Среда/загрузка** установите флажок **Скрыть системные объекты в обозревателе объектов**, а затем нажмите кнопку **ОК**.  
  
3.  В диалоговом окне **SQL Server Management Studio** нажмите кнопку **ОК** , чтобы подтвердить, что среда SQL Server Management Studio должна быть перезапущена для вступления в силу изменений.  
  
4.  Закройте и снова откройте среду SQL Server Management Studio.  
  
