---
title: PDO::exec
description: Справочник по API для функции PDO::exec в драйвере Microsoft PDO_SQLSRV для PHP для SQL Server.
ms.custom: ''
ms.date: 08/10/2020
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: 359a87c6-c13a-4518-8f23-a922e7f3b171
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: ad79792d21e9b097f6aee681b1097c8aacfa44fa
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99202021"
---
# <a name="pdoexec"></a>PDO::exec
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Подготавливает и выполняет инструкцию SQL в одном вызове функции, возвращая количество строк, затронутых этой инструкцией.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
int PDO::exec ($statement)  
```  
  
#### <a name="parameters"></a>Параметры  
*$statement*: строка, содержащая инструкцию SQL для выполнения.  
  
## <a name="return-value"></a>Возвращаемое значение  
Целое число, обозначающее количество затронутых строк.  
  
## <a name="remarks"></a>Remarks  
Если *$statement* содержит несколько инструкций SQL, количество затронутых строк указывается только для последней инструкции.  
  
PDO::exec не возвращает результаты для инструкции SELECT.  
  
Следующие атрибуты влияют на поведение PDO::exec:  
  
-   PDO::ATTR_DEFAULT_FETCH_MODE  
  
-   PDO::SQLSRV_ATTR_ENCODING  
  
-   PDO::SQLSRV_ATTR_QUERY_TIMEOUT  
  
Дополнительные сведения см. в статье [PDO::setAttribute](../../connect/php/pdo-setattribute.md). 
  
Поддержка PDO была добавлена в версии 2.0 [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)].  
  
## <a name="example"></a>Пример  
Этот пример удаляет строки таблицы Table1, содержащие "xxxyy" в столбце col1. Затем пример сообщает, сколько строк было удалено.  
  
```  
<?php  
   $c = new PDO( "sqlsrv:server=(local)");  
  
   $c->exec("use Test");  
   $ret = $c->exec("delete from Table1 where col1 = 'xxxyy'");  
   echo $ret;  
?>  
```  
  
## <a name="see-also"></a>См. также:  
[Класс PDO](../../connect/php/pdo-class.md)

[PDO](https://php.net/manual/book.pdo.php)  
  
