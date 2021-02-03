---
description: '&#x40;&#x40;LOCK_TIMEOUT (Transact-SQL)'
title: '@@LOCK_TIMEOUT (Transact-SQL) | Документы Майкрософт'
ms.custom: ''
ms.date: 09/19/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: reference
f1_keywords:
- '@@LOCK_TIMEOUT'
- '@@LOCK_TIMEOUT_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- timeout options [SQL Server], locks
- '@@LOCK_TIMEOUT function'
- current lock time-out setting
- locking [SQL Server], time-outs
ms.assetid: 6bf8bf97-60b8-40c1-b89d-8f5a00bcae2e
author: cawrites
ms.author: chadam
ms.openlocfilehash: 68181dbd097d0f61c8051ef5d3d113360bb52ada
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99200602"
---
# <a name="x40x40lock_timeout-transact-sql"></a>&#x40;&#x40;LOCK_TIMEOUT (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Возвращает значение времени ожидания блокировки в миллисекундах для текущего сеанса.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```syntaxsql  
@@LOCK_TIMEOUT  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="return-types"></a>Типы возвращаемых данных
 **integer**  
  
## <a name="remarks"></a>Комментарии  
 Инструкция SET LOCK_TIMEOUT позволяет установить в приложении максимальное время ожидания заблокированного ресурса. Если ожидание длится дольше значения LOCK_TIMEOUT, инструкция автоматически отменяется, а приложению возвращается сообщение об ошибке.  
  
 Функция @@LOCK_TIMEOUT возвращает значение –1 в случае, если в текущем сеансе этот параметр еще не был задан с помощью вызова SET LOCK_TIMEOUT.  
  
## <a name="examples"></a>Примеры  
 Данный пример иллюстрирует содержимое результирующего набора в случае не установленного заранее значения LOCK_TIMEOUT.  
  
```sql  
SELECT @@LOCK_TIMEOUT AS [Lock Timeout];  
GO  
```  
  
 Результирующий набор:  
  
```  
Lock Timeout  
------------  
-1  
```  
  
 В приведенном ниже примере значение LOCK_TIMEOUT устанавливается равным 1800 миллисекундам, после чего вызывается функция @@LOCK_TIMEOUT.  
  
```sql  
SET LOCK_TIMEOUT 1800;  
SELECT @@LOCK_TIMEOUT AS [Lock Timeout];  
GO  
```  
  
 Результирующий набор:  
  
```  
Lock Timeout  
------------  
1800          
```  
  
## <a name="see-also"></a>См. также  
 [Функции настройки (Transact-SQL)](../../t-sql/functions/configuration-functions-transact-sql.md)   
 [SET LOCK_TIMEOUT (Transact-SQL)](../../t-sql/statements/set-lock-timeout-transact-sql.md)  
  
  
