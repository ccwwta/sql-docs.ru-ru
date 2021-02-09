---
title: PDOStatement::errorInfo
description: Справочник по API для функции PDOStatement::errorInfo в драйвере Microsoft PDO_SQLSRV для PHP для SQL Server.
ms.custom: ''
ms.date: 01/29/2021
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: e45bebe8-ea4c-49b6-93db-cf1ae65f530c
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 0474b0c1225a248b47f0892ac940f2e58ab0efa0
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99206358"
---
# <a name="pdostatementerrorinfo"></a>PDOStatement::errorInfo
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Извлекает расширенные сведения об ошибке для последней операции с дескриптором инструкции.  
  
## <a name="syntax"></a>Синтаксис  

```
array PDOStatement::errorInfo();
```
  
## <a name="return-value"></a>Возвращаемое значение  
Массив сведений об ошибке для последней операции с дескриптором инструкции. Этот массив состоит из следующих полей:  
  
-   Код ошибки SQLSTATE.  
  
-   Код ошибки, относящийся к драйверу.  
  
-   Сообщение об ошибке, относящееся к драйверу.  
  
Если ошибка отсутствует или не задан SQLSTATE, поля, относящиеся к драйверу, будут иметь значение NULL.  
  
## <a name="remarks"></a>Remarks  
Поддержка PDO была добавлена в версии 2.0 [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)].  
  
## <a name="example"></a>Пример  
В этом примере инструкция SQL содержит ошибку, о которой затем сообщается.  
  
```php
<?php  
$conn = new PDO( "sqlsrv:server=(local) ; Database = AdventureWorks", "", "");  
$stmt = $conn->prepare('SELECT * FROM Person.Addressx');  
  
$stmt->execute();  
print_r ($stmt->errorInfo());  
?>  
```

## <a name="additional-odbc-messages"></a>Дополнительные сообщения ODBC

При возникновении исключения драйвер ODBC может вернуть несколько ошибок, которые помогают в диагностике проблем. Однако PDOStatement::errorInfo всегда выдает только первую ошибку. В ответ на этот [отчет об ошибке](https://bugs.php.net/bug.php?id=78196) функции [PDO::errorInfo](https://www.php.net/manual/en/pdo.errorinfo.php) и [PDOStatement::errorInfo](https://www.php.net/manual/en/pdostatement.errorinfo.php) были обновлены: теперь драйверы должны выводить *по крайней мере* следующие три поля:
```
0   SQLSTATE error code (a five characters alphanumeric identifier defined in the ANSI SQL standard).
1   Driver specific error code.
2   Driver specific error message.
```

Начиная с версии 5.9.0 функция PDOStatement::errorInfo по умолчанию выводит дополнительные ошибки ODBC при их наличии. Дополнительные сведения см. в разделе, посвященном [PDO::errorInfo](../../connect/php/pdo-errorinfo.md).
  
## <a name="see-also"></a>См. также:  
[Класс PDOStatement](../../connect/php/pdostatement-class.md)

[PDO::errorInfo](../../connect/php/pdo-errorinfo.md)

[PDO](https://php.net/manual/book.pdo.php)  
  
