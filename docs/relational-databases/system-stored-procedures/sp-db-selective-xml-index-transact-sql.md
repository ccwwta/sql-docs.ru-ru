---
description: sp_db_selective_xml_index (Transact-SQL)
title: sp_db_selective_xml_index (Transact-SQL)
ms.custom: ''
ms.date: 02/11/2021
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sp_db_selective_xml_index_TSQL
- sp_db_selective_xml_index
dev_langs:
- TSQL
helpviewer_keywords:
- sp_db_selective_xml_index procedure
author: markingmyname
ms.author: maghan
ms.openlocfilehash: ed30d2b8df6141b308d32dee8f2fdcec0c2eceb1
ms.sourcegitcommit: c83c17e44b5e1e3e2a3b5933c2a1c4afb98eb772
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "100525180"
---
# <a name="sp_db_selective_xml_index-transact-sql"></a>sp_db_selective_xml_index (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Включает и выключает функциональность селективного XML-индекса в базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. При вызове без параметров хранимая процедура возвращает 1, если селективный XML-индекс включен в определенной базе данных.  

> [!NOTE]  
> Начиная с [!INCLUDE[sssql14-md](../../includes/sssql14-md.md)] , функциональность селективного XML-индекса не может быть отключена. [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] В [!INCLUDE[sssql11-md](../../includes/sssql11-md.md)] для отключения функции селективного XML-индекса с помощью этой хранимой процедуры база данных должна быть размещена в простой модели восстановления с помощью [параметров ALTER database Set &#40;TRANSACT-SQL&#41;](../../t-sql/statements/alter-database-transact-sql-set-options.md) .  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```syntaxsql
  
      sys.sp_db_selective_xml_index[[ @dbname = ] 'dbname'],   
[[ @selective_xml_index = ] 'selective_xml_index']  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @ dbname = ] 'dbname'` Имя базы данных, для которой необходимо включить или отключить селективный XML-индекс. Если значение *dbname* равно null, предполагается, что используется текущая база данных. *@dbname* аргумент имеет тип **sysname**.


`[ @selective_xml_index = ] 'selective_xml_index'` Определяет, следует ли включать или отключать индекс. Допустимые значения: "on", "OFF", "true", "false". Если передается другое значение, кроме on, "true", "OFF" или "false", возникнет ошибка. *@selective_xml_index* имеет тип **varchar (6)**.

  
## <a name="return-code-values"></a>Значения кода возврата  
 **1** , если СЕЛЕКТИВНЫЙ XML-индекс включен в определенной базе данных, **0** , если он отключен.  
  
## <a name="examples"></a>Примеры  
  
### <a name="a-enable-selective-xml-index-functionality"></a>A. Включение функциональности селективного XML-индекса  
 В следующем примере включается селективный XML-индекс в текущей базе данных.  
  
```sql
EXECUTE sys.sp_db_selective_xml_index  
    @dbname = NULL  
  , @selective_xml_index = N'on';  
GO  
```  
  
 В следующем примере включается селективный XML-индекс в базе данных AdventureWorks2012.  
  
```sql
EXECUTE sys.sp_db_selective_xml_index  
    @dbname = N'AdventureWorks2012'  
  , @selective_xml_index = N'true';  
GO  
```  
  
### <a name="b-disable-selective-xml-index-functionality"></a>Б. Отключение возможностей селективного XML-индекса  
 В следующем примере выключается селективный XML-индекс в текущей базе данных.  
  
```sql
EXECUTE sys.sp_db_selective_xml_index  
    @dbname = NULL  
  , @selective_xml_index = N'off';  
GO  
```  
  
 В следующем примере выключается селективный XML-индекс в базе данных AdventureWorks2012.  
  
```sql
EXECUTE sys.sp_db_selective_xml_index  
    @dbname = N'AdventureWorks2012'  
  , @selective_xml_index = N'false';  
GO  
```  
  
### <a name="c-detect-if-selective-xml-index-is-enabled"></a>В. Включен ли селективный XML-индекс  
 В следующем примере определяется наличие селективного XML-индекса. Возвращает 1, если селективный XML-индекс включен.  
  
```sql
EXECUTE sys.sp_db_selective_xml_index;  
GO  
```  
  
## <a name="see-also"></a>См. также:  
 [Выборочный XML-индекс (SXI)](../../relational-databases/xml/selective-xml-indexes-sxi.md)  
   