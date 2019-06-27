---
title: Функциональные ограничения | Документация Майкрософт
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
author: vainolo
ms.author: arib
manager: tomerw
monikerRange: '>= sql-server-ver15 || = sqlallproducts-allversions'
ms.openlocfilehash: 99a0a768334ab5335591fae69e4f18060fba9866
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2019
ms.locfileid: "66506922"
---
# <a name="feature-restrictions"></a>Функциональные ограничения

[!INCLUDE[tsql-appliesto-ssver15-xxxx-xxxx-xxx](../../includes/tsql-appliesto-ssver15-xxxx-xxxx-xxx.md)]

Один из общих источников атак SQL Server — через веб-приложения, которые обращаются к базе данных; здесь используются различные виды атак путем внедрения кода SQL, чтобы собрать сведения о базе данных.  В идеале код приложения разрабатывается так, чтобы не допускать внедрения кода SQL.  Тем не менее в крупных-базах кода, которые включают прежние версии и внешний код, невозможно убедиться, что были предусмотрены все случаи, поэтому защита от атак внедрением кода SQL необходима.  Функциональные ограничения предназначены для предотвращения утечки сведений о базе данных при атаках путем внедрения кода SQL даже в том случае, если внедрение кода SQL выполнено успешно.

## <a name="enabling-feature-restrictions"></a>Включение функциональных ограничений

Включение функциональных ограничений выполняется с помощью хранимой процедуры `sp_add_feature_restriction` следующим образом:

```sql
EXEC sp_add_feature_restriction <feature>, <object_class>, <object_name>
```

Следующие функции могут быть ограничены:

| Компонент          | Описание |
|------------------|-------------|
| N'ErrorMessages' | При ограничении будут замаскированы все данные в сообщении об ошибке. См. раздел [Функциональные ограничения в сообщениях об ошибках](#error-messages-feature-restriction) |
| N'Waitfor'       | При ограничении команда сразу возвращает управление без задержки. См. раздел [Функциональные ограничения WAITFOR](#waitfor-feature-restriction) |

Значением `object_class` может быть либо `N'User'`, либо `N'Role'` для обозначения того, что `object_name` — имя пользователя или соответственно имя роли в базе данных.

В следующем примере все сообщения об ошибках для пользователя `MyUser` маскируются:

```sql
EXEC sp_add_feature_restriction N'ErrorMessages', N'User', N'MyUser'
```

## <a name="disabling-feature-restrictions"></a>Отключение функциональных ограничений

Отключение функциональных ограничений выполняется с помощью хранимой процедуры `sp_drop_feature_restriction` следующим образом:

```sql
EXEC sp_drop_feature_restriction <feature>, <object_class>, <object_name>
```

В следующем примере отключается маскировка сообщений об ошибках для пользователя `MyUser`:

```sql
EXEC sp_drop_feature_restriction N'ErrorMessages', N'User', N'MyUser'
```

## <a name="viewing-feature-restrictions"></a>Просмотр функциональных ограничений

Представление `sys.sql_feature_restrictions` включает все определенные сейчас функциональные ограничения в базе данных. Подробности см. в разделе [sys.sql_feature_restrictions](../system-catalog-views/sys-sql-feature-restrictions.md).

## <a name="feature-restrictions"></a>Функциональные ограничения

### <a name="error-messages-feature-restriction"></a>Функциональные ограничения в сообщениях об ошибках

Один из обычных способов атаки путем внедрения кода SQL — вставка кода, который вызывает ошибку.  Изучив сообщение об ошибке, злоумышленник может получить сведения о системе для более целенаправленных атак.  Эта атака может быть особенно полезной, если приложение не отображает результаты запроса, но отображает сообщения об ошибках.

Рассмотрим приложение с запросом в следующем виде:

```html
http://www.contoso.com/employee.php?id=1
```

Оно выполняет следующий запрос к базе данных:

```sql
SELECT Name FROM EMPLOYEES WHERE Id=$EmpId
```

Если значение, переданное в качестве параметра `Id` в запроса к веб-приложению, копируется вместо $EmpId в запрос к базе данных, злоумышленник может сделать следующий запрос:

```html
http://www.contoso.com/employee.php?id=1 AND CAST(DB_NAME() AS INT)=0
```

Будет возвращена следующая ошибка, что позволит злоумышленнику узнать имя базы данных:

```sql
Conversion failed when converting the nvarchar value 'HR_Data' to data type int.
```

После функционального ограничения сообщений об ошибках для пользователя приложения в базе данных производится маскировка сообщения об ошибке и не происходит утечка внутренних данных:

```sql
Conversion failed when converting the ****** value '******' to data type ******.
```

Аналогичным образом злоумышленник может сделать следующий запрос:

```html
http://www.contoso.com/employee.php?id=1 AND CAST(Salary AS TINYINT)=0
```

Будет возвращена следующая ошибка, что позволит злоумышленнику узнать зарплату сотрудника:

```sql
Arithmetic overflow error for data type tinyint, value = 140000.
```

Функциональные ограничения сообщений об ошибках позволяют базе данных вернуть следующее:

```sql
Arithmetic overflow error for data type ******, value = ******.
```

### <a name="waitfor-feature-restriction"></a>Функциональные ограничения WAITFOR

Слепое внедрение кода SQL — это ситуация, когда приложение не предоставляет злоумышленнику результаты внедренного SQL или сообщение об ошибке, но злоумышленник может получить сведения из базы данных, создав условный запрос, в котором две условные ветви имеют разное время выполнения. Сравнивая время отклика, злоумышленник может узнать, какая ветвь была выполнена, и тем самым получить дополнительные сведения о системе. Самый простой вариант подобной атаки — использование инструкции `WAITFOR` для добавления задержки.

Рассмотрим приложение с запросом в следующем виде:

```html
http://www.contoso.com/employee.php?id=1
```

Оно выполняет следующий запрос к базе данных:

```sql
SELECT Name FROM EMPLOYEES WHERE Id=$EmpId
```

Если значение, переданное в качестве параметра `Id` в запроса к веб-приложению, копируется вместо $EmpId в запрос к базе данных, злоумышленник может сделать следующий запрос:

```html
http://www.contoso.com/employee.php?id=1; IF SYSTEM_USER='sa' WAITFOR DELAY '00:00:05'
```

Такой запрос будет длиться дополнительные 5 секунд, если использовалась учетная запись `sa`. Если в базе данных включены функциональные ограничения `WAITFOR`, инструкция `WAITFOR` будет игнорироваться и утечка сведений при такой атаке не происходит.