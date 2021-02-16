---
description: catalog.stop_operation (база данных SSISDB)
title: catalog.stop_operation (база данных SSISDB) | Документы Майкрософт
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: language-reference
ms.assetid: 97fd9d22-03dd-4eda-8f6c-ba8b67acec68
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1d215f7d53fcc525fdc6aca43c43df25a827ed6e
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100346747"
---
# <a name="catalogstop_operation-ssisdb-database"></a>catalog.stop_operation (база данных SSISDB)

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Останавливает проверку или экземпляр выполнения в каталоге служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
catalog.stop_operation [ @operation_id = ] operation_id  
```  
  
## <a name="arguments"></a>Аргументы  
 [ @operation_id = ] *operation_id*  
 Уникальный идентификатор проверки или экземпляра выполнения. Параметр *operation_id* имеет тип **bigint**.  
  
## <a name="return-code-value"></a>Значения кодов возврата  
 0 (успешное завершение)  
  
## <a name="result-sets"></a>Результирующие наборы  
 None  
  
## <a name="permissions"></a>Разрешения  
 Эта хранимая процедура требует применения одного из следующих разрешений:  
  
-   Разрешения READ и MODIFY на проверку или экземпляр выполнения.  
  
-   Членство в роли базы данных **ssis_admin**  
  
-   Членство в роли сервера **sysadmin**  
  
## <a name="errors-and-warnings"></a>Ошибки и предупреждения  
 Следующий список содержит описания некоторых условий, которые могут вызвать ошибку или предупреждение.  
  
-   Пользователь не имеет соответствующих разрешений  
  
-   Недопустимый идентификатор операции  
  
-   Операция уже остановлена  
  
## <a name="remarks"></a>Примечания  
 Только один пользователь за раз должен останавливать операцию в каталоге служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]. Если несколько пользователей попытаются остановить операцию, хранимая процедура возвратит код успешного завершения при первой попытке (значение `0`), но последующие попытки будут приводить к ошибкам.  
  
  
