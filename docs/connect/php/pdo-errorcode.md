---
title: PDO::errorCode
description: Справочник по API для функции PDO::errorCode в драйвере Microsoft PDO_SQLSRV для PHP для SQL Server.
ms.custom: ''
ms.date: 08/10/2020
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: 5864b1d8-6814-41cd-a88d-415124484c13
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: ed2a580a972375a14c5ed6532e40eb7db43373a5
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99202036"
---
# <a name="pdoerrorcode"></a>PDO::errorCode
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

PDO::errorCode извлекает значение SQLSTATE последней операции для дескриптора базы данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
mixed PDO::errorCode();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
PDO::errorCode возвращает пятисимвольный SQLSTATE в виде строки или значение NULL в случае отсутствия операции для дескриптора базы данных.  
  
## <a name="remarks"></a>Remarks  
Для некоторых успешных операций PDO::errorCode в драйвере PDO_SQLSRV возвращает предупреждения. Например, для успешного подключения PDO::errorCode возвращает значение "01000", указывающее SQL_SUCCESS_WITH_INFO.  
  
PDO::errorCode возвращает только сведения об ошибках для операций, выполненных непосредственно для подключения к базе данных. Если вы создаете экземпляр PDOStatement через PDO::prepare или PDO::query и для объекта инструкции формируется ошибка, PDO::errorCode не получает эту ошибку. Необходимо вызвать метод PDOStatement::errorCode, чтобы возвратить код ошибки для операции, выполненной с определенным объектом инструкции.  
  
Поддержка PDO была добавлена в версии 2.0 [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)].  
  
## <a name="example"></a>Пример  
В этом примере неправильно указано имя столбца (`Cityx` вместо `City`), что вызывает ошибку, о которой затем сообщается.  
  
```  
<?php  
$conn = new PDO( "sqlsrv:server=(local) ; Database = AdventureWorks ", "", "");  
$query = "SELECT * FROM Person.Address where Cityx = 'Essen'";  
  
$conn->query($query);  
print $conn->errorCode();  
?>  
```  
  
## <a name="see-also"></a>См. также:  
[Класс PDO](../../connect/php/pdo-class.md)

[PDO](https://php.net/manual/book.pdo.php)  
  
