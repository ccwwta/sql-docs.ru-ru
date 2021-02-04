---
description: Отмена подавления предупреждений для пользовательских отчетов
title: Отмена подавления предупреждений для пользовательских отчетов
ms.custom: seo-lt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], custom reports
ms.assetid: 0deed900-c910-4d12-aac0-6ab9e39eb068
author: markingmyname
ms.author: maghan
ms.openlocfilehash: cf87ce7e04e50ea64a6f98db0b29dfc7e90f813d
ms.sourcegitcommit: 38e055eda82d293bf5fe9db14549666cf0d0f3c0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2021
ms.locfileid: "99250493"
---
# <a name="unsuppress-run-custom-report-warnings"></a>Отмена подавления предупреждений для пользовательских отчетов
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]
Для пользовательских отчетов предусмотрено два типа предупреждающих диалоговых окон. В этом разделе описано, как отменить подавление отображения этих полей в [!INCLUDE[ssnoversion](../../includes/ssnoversion-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
По умолчанию перед запуском пользовательского отчета отображается диалоговое окно **Запустить пользовательский отчет** . Если установить флажок **Больше не показывать это предупреждение** , то это диалоговое окно больше отображаться не будет. Также по умолчанию диалоговое окно **Запустить пользовательский отчет** отображается, если после открытия одного пользовательского отчета нажать ссылку для открытия другого отчета. В этом диалоговом окне отображается полный путь к файлу пользовательского детализированного отчета. Если установить флажок **Больше не показывать это предупреждение** , то это диалоговое окно больше отображаться не будет.  
  
## <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a>Использование среды SQL Server Management Studio  
  
#### <a name="to-unsuppress-the-main-custom-report-warning-dialog-box"></a>Отмена подавления основного диалогового окна предупреждения для пользовательских отчетов  
  
1.  Подключитесь к файлу \<*Server*>\\<*Общая папка*>|\<*Drive*>\Documents and Settings\\<UserProfile>\Application Data\Microsoft\Microsoft SQL Server\130\Tools\Shell\reports.xml.  
  
2.  Щелкните правой кнопкой мыши файл **reports.xml** и выберите команду **Изменить**.  
  
3.  Измените **<SuppressWarning>true\<\/SuppressWarning> на <SuppressWarning>false\<\/SuppressWarning>** .  
  
4.  Перезапустите [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
#### <a name="to-unsuppress-the-drill-through-custom-report-warning-dialog-box"></a>Отмена подавления диалогового окна предупреждений для детализированных пользовательских отчетов  
  
1.  Подключитесь к файлу \<*Server*>\\<*Общая папка*>|\<*Drive*>\Documents and Settings\\<UserProfile>\Application Data\Microsoft\Microsoft SQL Server\130\Tools\Shell\reports.xml.  
  
2.  Щелкните правой кнопкой мыши файл **reports.xml** и выберите команду **Изменить**.  
  
3.  Измените **<SuppressDrillthroughWarning>true\<\/SuppressDrillthroughWarning> на <SuppressDrillthroughWarning>false\<\/SuppressDrillthroughWarning>** .  
  
4.  Перезапустите [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
## <a name="see-also"></a>См. также:  
[Пользовательские отчеты в среде Management Studio](../../ssms/object/custom-reports-in-management-studio.md)  
[Добавление пользовательского отчета в среду Management Studio](../../ssms/object/add-a-custom-report-to-management-studio.md)  
[Использование пользовательских отчетов для свойств узлов обозревателя объектов](../../ssms/object/use-custom-reports-with-object-explorer-node-properties.md)  
  
