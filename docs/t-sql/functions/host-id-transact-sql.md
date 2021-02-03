---
description: Функция HOST_ID (Transact-SQL)
title: HOST_ID (Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: reference
f1_keywords:
- HOST_ID
- HOST_ID_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- IDs [SQL Server], workstations
- HOST_ID function
- workstation IDs [SQL Server]
- identification numbers [SQL Server], workstations
ms.assetid: 36ba56d4-20d7-4cd1-aa2a-e40a6c0a4e39
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: bfd14c50d3f4b566c3be442631278eca8ffc661f
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99159217"
---
# <a name="host_id-transact-sql"></a>Функция HOST_ID (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Возвращает идентификационный номер рабочей станции. Идентификационным номером рабочей станции служит идентификатор процесса приложения на клиентском компьютере, который подключается к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```syntaxsql
HOST_ID ()  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="return-types"></a>Типы возвращаемых данных
 **char(10)**  
  
## <a name="remarks"></a>Комментарии  
 Если параметр системной функции является необязательным, то предполагаются текущие база данных, главный компьютер, пользователь сервера или пользователь базы данных. За встроенными функциями всегда должны следовать круглые скобки.  
  
 Системные функции можно использовать в списке выбора, в предложении WHERE и в любом месте, где разрешается использование выражений.  
  
## <a name="examples"></a>Примеры  
 Следующий пример создает таблицу, которая использует `HOST_ID()` в определении `DEFAULT` для записи идентификаторов терминалов компьютеров, которые вставляют строки в таблицу регистрации заказов.  
  
```sql  
CREATE TABLE Orders  
   (OrderID     INT       PRIMARY KEY,  
    CustomerID  NCHAR(5)  REFERENCES Customers(CustomerID),  
    TerminalID  CHAR(8)   NOT NULL DEFAULT HOST_ID(),  
    OrderDate   DATETIME  NOT NULL,  
    ShipDate    DATETIME  NULL,  
    ShipperID   INT       NULL REFERENCES Shippers(ShipperID));  
GO  
```  
  
## <a name="see-also"></a>См. также:  
 [Выражения (Transact-SQL)](../../t-sql/language-elements/expressions-transact-sql.md)   
 [Системные функции (Transact-SQL)](../../relational-databases/system-functions/system-functions-category-transact-sql.md)  
  
  
