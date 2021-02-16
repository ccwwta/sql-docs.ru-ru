---
description: catalog.startup
title: catalog.startup | Документы Майкрософт
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: language-reference
ms.assetid: 271fd405-246a-4852-bfbe-f557241ce6ea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2dc49249c3122c41d89ff8e9457484539ed2f836
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100352763"
---
# <a name="catalogstartup"></a>catalog.startup 

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Осуществляет обслуживание состояния операций для каталога SSISDB.  
  
 Хранимая процедура исправляет состояние любых пакетов, выполнявшихся в момент отключения экземпляра сервера служб [!INCLUDE[ssIS](../../includes/ssis-md.md)].  
  
 Предусмотрена возможность включить хранимую процедуру для автоматического выполнения при каждом перезапуске экземпляра сервера [!INCLUDE[ssIS](../../includes/ssis-md.md)], выбрав параметр **Включить автоматическое выполнение хранимой процедуры служб Integration Services при запуске SQL Server** в диалоговом окне **Создание каталога**.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
catalog.startup  
```  
  
## <a name="return-code-value"></a>Значения кодов возврата  
 0 (успешное завершение)  
  
## <a name="result-sets"></a>Результирующие наборы  
 None  
  
## <a name="permissions"></a>Разрешения  
 Эта хранимая процедура требует применения одного из следующих разрешений:  
  
-   Разрешения READ и MODIFY на экземпляр выполнения, разрешения READ и EXECUTE на проект и, при необходимости, разрешения READ на среду, указанную в ссылке  
  
-   Членство в роли базы данных **ssis_admin**  
  
-   Членство в роли сервера **sysadmin**  
  
  
