---
description: IsDescendantOf (компонент Database Engine)
title: IsDescendantOf (ядро СУБД) | Документы Майкрософт
ms.custom: ''
ms.date: 07/22/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: reference
f1_keywords:
- IsDescendant_TSQL
- IsDescendant
dev_langs:
- TSQL
helpviewer_keywords:
- IsDescendantOf [Database Engine]
ms.assetid: edc80444-b697-410f-9419-0f63c9b5618d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a3ffb6820f43553a6adcc2f613d93657b23b79f9
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99165099"
---
# <a name="isdescendantof-database-engine"></a>IsDescendantOf (компонент Database Engine)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

Возвращает значение true, если *this* является потомком родительского элемента.
  
## <a name="syntax"></a>Синтаксис  
  
```syntaxsql
-- Transact-SQL syntax  
child. IsDescendantOf ( parent )  
```  
  
```syntaxsql
-- CLR syntax  
SqlHierarchyId IsDescendantOf (SqlHierarchyId parent )  
```  

[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>Аргументы
*parent*  
Узел **hierarchyid**, для которого следует выполнить проверку IsDescendantOf.
  
## <a name="return-types"></a>Типы возвращаемых данных  
**Возвращаемый тип SQL Server:bit**
  
**Возвращаемый тип CLR:SqlBoolean**
  
## <a name="remarks"></a>Комментарии  
Возвращает значение true для всех узлов поддерева, корнем для которых является родительский элемент, и значение false для всех остальных узлов.
  
Родительский элемент считается своим собственным потомком.
  
## <a name="examples"></a>Примеры  
  
### <a name="a-using-isdescendantof-in-a-where-clause"></a>A. Использование функции IsDescendantOf в предложении WHERE  
В следующем примере возвращается имя руководителя и имена подотчетных ему сотрудников:
  
```sql
DECLARE @Manager hierarchyid  
SELECT @Manager = OrgNode FROM HumanResources.EmployeeDemo  
  WHERE LoginID = 'adventure-works\dylan0'  
  
SELECT * FROM HumanResources.EmployeeDemo  
WHERE OrgNode.IsDescendantOf(@Manager) = 1  
```  
  
### <a name="b-using-isdescendantof-to-evaluate-a-relationship"></a>Б. Использование функции IsDescendantOf для оценки связи  
В следующем фрагменте кода объявляются и заполняются три переменные. Затем оценивается иерархическая связь и возвращается один из двух печатаемых результатов на основе сравнения:
  
```sql
DECLARE @Manager hierarchyid, @Employee hierarchyid, @LoginID nvarchar(256)  
SELECT @Manager = OrgNode FROM HumanResources.EmployeeDemo  
WHERE LoginID = 'adventure-works\terri0' ;  
  
SELECT @Employee = OrgNode, @LoginID = LoginID FROM HumanResources.EmployeeDemo  
  WHERE LoginID = 'adventure-works\rob0'  
  
IF @Employee.IsDescendantOf(@Manager) = 1  
   BEGIN  
    PRINT 'LoginID ' + @LoginID + ' is a subordinate of the selected Manager.'  
   END  
ELSE  
   BEGIN  
    PRINT 'LoginID ' + @LoginID + ' is not a subordinate of the selected Manager.' ;  
   END  
```  
  
### <a name="c-calling-a-common-language-runtime-method"></a>В. Вызов метода CLR  
В следующем фрагменте кода вызывается метод `IsDescendantOf()`.
  
```sql
this.IsDescendantOf(Parent)  
```  
  
## <a name="see-also"></a>См. также раздел
[Справочник по методам типа данных hierarchyid](./hierarchyid-data-type-method-reference.md)  
[Иерархические данные (SQL Server)](../../relational-databases/hierarchical-data-sql-server.md)  
[hierarchyid (Transact-SQL)](../../t-sql/data-types/hierarchyid-data-type-method-reference.md)
  
