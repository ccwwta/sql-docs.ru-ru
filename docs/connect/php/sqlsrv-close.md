---
description: sqlsrv_close
title: sqlsrv_close | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- sqlsrv_close
apitype: NA
helpviewer_keywords:
- sqlsrv_close
- API Reference, sqlsrv_close
ms.assetid: 6ac6209c-a134-4f8f-b88b-8eefaa1cbc7f
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 16dfb43ebc8a35ef1a3e6016092f67e328d1eda5
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99190720"
---
# <a name="sqlsrv_close"></a>sqlsrv_close
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Закрывает указанное подключение и освобождает связанные ресурсы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sqlsrv_close( resource $conn )  
```  
  
#### <a name="parameters"></a>Параметры  
*$conn*: закрываемое подключение.  
  
## <a name="return-value"></a>Возвращаемое значение  
Логическое значение **true** , если только функция не вызывается с недопустимым параметром. Если функция вызывается с недопустимым параметром, возвращается значение **false** .  
  
> [!NOTE]  
> **Null** является допустимым параметром для этой функции. Это позволяет несколько раз вызывать функцию в скрипте. Например, если вы закроете подключение в условии ошибки, а затем снова закроете его снова в конце сценария, второй вызов **sqlsrv_close** возвратит значение **true** (истина), так как первый вызов **sqlsrv_close** (в условии ошибки) задает для ресурса подключения значение **NULL**.  
  
## <a name="example"></a>Пример  
В следующем примере выполняется закрытие подключения. В примере предполагается, что SQL Server установлен на локальном компьютере. При выполнении примера из командной строки все выходные данные выводятся в консоль.  
  
```  
<?php  
/*Connect to the local server using Windows Authentication and   
specify the AdventureWorks database as the database in use. */  
$serverName = "(local)";  
$conn = sqlsrv_connect( $serverName);  
if( $conn === false )  
{  
     echo "Could not connect.\n";  
     die( print_r( sqlsrv_errors(), true));  
}  
  
//-----------------------------------------------  
// Perform operations with connection here.  
//-----------------------------------------------  
  
/* Close the connection. */  
sqlsrv_close( $conn);  
echo "Connection closed.\n";  
?>  
```  
  
## <a name="see-also"></a>См. также:  
[Справочник по API для драйвера SQLSRV](../../connect/php/sqlsrv-driver-api-reference.md)

[Информация о примерах кода в документации](../../connect/php/about-code-examples-in-the-documentation.md)  
  
