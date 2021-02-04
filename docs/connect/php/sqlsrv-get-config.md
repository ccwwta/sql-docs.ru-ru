---
description: sqlsrv_get_config
title: sqlsrv_get_config | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- sqlsrv_get_config
apitype: NA
helpviewer_keywords:
- API Reference, sqlsrv_get_config
- sqlsrv_get_config
ms.assetid: ce2befc2-af98-45bb-8d41-60f1674dccfc
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: a59f7be566ab349ae6edd3eabf6ed99c32dc707f
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99154103"
---
# <a name="sqlsrv_get_config"></a>sqlsrv_get_config
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Возвращает текущее значение указанного параметра конфигурации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sqlsrv_get_config( string $setting )  
```  
  
#### <a name="parameters"></a>Параметры  
*$setting*: параметр конфигурации, для которого возвращается значение. Список настраиваемых параметров см. в статье [sqlsrv_configure](../../connect/php/sqlsrv-configure.md).  
  
## <a name="return-value"></a>Возвращаемое значение  
Значение параметра, определяемое параметром *$setting* . Если указано недопустимое значение, возвращается значение **false** , а в коллекцию ошибок добавляется ошибка.  
  
## <a name="remarks"></a>Комментарии  
Если **false** config **sqlsrv_get_config**, необходимо вызвать [sqlsrv_errors](../../connect/php/sqlsrv-errors.md) , чтобы определить, произошла ли ошибка или значение **false** параметра определено параметром *$setting* .  
  
## <a name="see-also"></a>См. также:  
[Справочник по API для драйвера SQLSRV](../../connect/php/sqlsrv-driver-api-reference.md)  

[sqlsrv_configure](../../connect/php/sqlsrv-configure.md)  

[sqlsrv_errors](../../connect/php/sqlsrv-errors.md)  
  
