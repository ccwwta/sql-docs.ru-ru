---
description: catalog.update_master_address (база данных SSISDB)
title: catalog.update_master_address (база данных SSISDB) | Документы Майкрософт
ms.custom: ''
ms.date: 07/18/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: language-reference
author: haoqian
ms.author: haoqian
monikerRange: '>= sql-server-2017'
ms.openlocfilehash: 666345dbcf16c1b4839abc9b001044722c7199d2
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100346787"
---
# <a name="catalogupdate_master_address-ssisdb-database"></a>catalog.update_master_address (база данных SSISDB)

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


[!INCLUDE[sqlserver2017](../../includes/applies-to-version/sqlserver2017.md)]

Обновите главную конечную точку [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Scale Out.

## <a name="syntax"></a>Синтаксис

```sql
catalog.update_master_address [ @MasterAddress = ] masterAddress
```

## <a name="arguments"></a>Аргументы
[ @MasterAddress = ] *masterAddress*  
Главная конечная точка Scale Out. Параметр *masterAddress* имеет тип **nvarchar**.  

 ## <a name="return-code-value"></a>Значения кодов возврата  
 0 (успешное завершение)  
  
## <a name="result-sets"></a>Результирующие наборы  
 None  

## <a name="permissions"></a>Разрешения  
 Эта хранимая процедура требует применения одного из следующих разрешений:  
   
-   Членство в роли базы данных **ssis_admin**  
  
-   Членство в роли сервера **sysadmin**  
 
