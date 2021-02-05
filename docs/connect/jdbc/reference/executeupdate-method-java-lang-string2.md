---
description: Метод executeUpdate (java.lang.String)
title: Метод executeUpdate | Документация Майкрософт
ms.custom: ''
ms.date: 02/07/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerPreparedStatement.executeUpdate (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 91ecb1cd-001d-4ac9-9ae8-5db05c3c2959
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 8ce4dff5d7b17b1d88670189fa119d6a1c81915b
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99168431"
---
# <a name="executeupdate-method-javalangstring"></a>Метод executeUpdate (java.lang.String)

Выполняет заданную инструкцию SQL, которой может быть инструкция INSERT, UPDATE, MERGE или DELETE, либо инструкцию SQL, не возвращающую значения, например инструкцию SQL DDL.

## <a name="syntax"></a>Синтаксис

```
public final int executeUpdate(java.lang.String sql)
```

#### <a name="parameters"></a>Параметры
*sql*

Значение типа **String**, содержащее инструкцию SQL.

## <a name="return-value"></a>Возвращаемое значение
Значение типа **int**, указывающее либо число обработанных строк, либо значение 0 для инструкций языка DDL.

## <a name="exceptions"></a>Исключения
[SQLServerException](./sqlserverexception-class.md)

## <a name="remarks"></a>Remarks
Этот метод executeUpdate определен с помощью метода executeUpdate в интерфейсе java.sql.PreparedStatement.

Вызов этого метода приводит к исключению, поскольку инструкция SQL для объекта SQLServerPreparedStatement определена при создании объекта.

## <a name="see-also"></a>См. также:

[Метод executeUpdate (SQLServerPreparedStatement)](./executeupdate-method-sqlserverpreparedstatement.md)

[Члены SQLServerPreparedStatement](./sqlserverpreparedstatement-members.md)

[Класс SQLServerPreparedStatement](./sqlserverpreparedstatement-class.md)
