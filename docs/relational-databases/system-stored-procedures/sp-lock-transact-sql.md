---
description: sp_lock (Transact-SQL)
title: sp_lock (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- sp_lock_TSQL
- sp_lock
dev_langs:
- TSQL
helpviewer_keywords:
- sp_lock
ms.assetid: 9eaa0ec2-2ad9-457c-ae48-8da92a03dcb0
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 09e753e8b821c3ad8029a7ed4d81bbe183160279
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99185383"
---
# <a name="sp_lock-transact-sql"></a>sp_lock (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Сообщает сведения о блокировках.  
  
> [!IMPORTANT]  
> [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] Чтобы получить сведения о блокировках в [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , используйте динамическое административное представление [sys.dm_tran_locks](../../relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql.md) .  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
sp_lock [ [ @spid1 = ] 'session ID1' ] [ , [@spid2 = ] 'session ID2' ]  
[ ; ]  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @spid1 = ] 'session ID1'`[!INCLUDE[ssDE](../../includes/ssde-md.md)]Идентификатор сеанса из **sys.dm_exec_sessions** , для которого пользователю требуется информация о блокировке. *session ID1* имеет **тип int** и значение по умолчанию NULL. Выполните **sp_who** , чтобы получить сведения о ходе сеанса. Если параметр *session ID1* не указан, отображаются сведения обо всех блокировках.  
  
`[ @spid2 = ] 'session ID2'` Другой [!INCLUDE[ssDE](../../includes/ssde-md.md)] идентификатор сеанса из **sys.dm_exec_sessions** , который может иметь блокировку одновременно с *сеансом id1* и сведениями о том, что пользователь хочет получить информацию. *Session id2* имеет **тип int** и значение по умолчанию NULL.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 0 (успешное завершение)  
  
## <a name="result-sets"></a>Результирующие наборы  
 Результирующий набор **sp_lock** содержит по одной строке для каждой блокировки, удерживаемой сеансами, указанными в параметрах **\@ SPID1** и **\@ SPID2** . Если не указано ни **\@ SPID1** , ни **\@ SPID2** , результирующий набор сообщает о блокировках для всех сеансов, активных в данный момент в экземпляре [!INCLUDE[ssDE](../../includes/ssde-md.md)] .  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**spid**|**smallint**|Числовой идентификатор сеанса компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] для процесса, запрашивающего блокировку.|  
|**DBID**|**smallint**|Числовой идентификатор базы данных, в которой удерживается блокировка. Для идентификации базы данных можно использовать функцию DB_NAME().|  
|**ObjId**|**int**|Числовой идентификатор объекта, на который удерживается блокировка. Для идентификации объекта можно использовать функцию OBJECT_NAME() в связанной базе данных. Значение 99 является особым, и означает блокировку на одной из системных страниц, используемых для записи распределенных страниц в базе данных.|  
|**IndId**|**smallint**|Числовой идентификатор индекса, для которого удерживается блокировка.|  
|**Type**|**nchar (4)**|Типы блокировки:<br /><br /> RID = Блокировка на одну строку в таблице, задаваемой идентификатором строки (RID — row ID);<br /><br /> KEY = Блокировка внутри индекса, которая защищает диапазон ключей в сериализуемых транзакциях;<br /><br /> PAG = Блокировка данных или индексной страницы;<br /><br /> EXT = Блокировка на экстент.<br /><br /> TAB = Блокировка на целую таблицу, включая все данные и индексы;<br /><br /> DB = Блокировка на базу данных;<br /><br /> FIL = Блокировка на файл базы данных;<br /><br /> APP = Блокировка на ресурс приложения;<br /><br /> MD = Блокировка на метаданные или данные о каталоге;<br /><br /> ХБТ = блокировка в куче или сбалансированном дереве (HoBT). Эти сведения неполные в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].<br /><br /> AU = Блокировка на единицу распределения (allocation unit). Эти сведения неполные в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].|  
|**Ресурс**|**nchar (32)**|Значение, определяющее блокируемый ресурс. Формат значения зависит от типа ресурса, определенного в столбце **тип** :<br /><br /> **Тип** Значение: значение **ресурса**<br /><br /> RID: идентификатор в формате ИД файла: PageNumber: RID, где идентификатор файла определяет файл, содержащий страницу, PageNumber определяет страницу, содержащую строку, а RID определяет конкретную строку на странице. параметр ИД соответствует столбцу **file_id** в представлении каталога **sys.database_files** .<br /><br /> KEY: шестнадцатеричное число, используемое внутренним компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)] .<br /><br /> PAG: число в формате ИД файла: PageNumber, где "ИД" определяет файл, содержащий страницу, а PageNumber определяет страницу.<br /><br /> EXT — номер, определяющий первую страницу в экстенте. Число в формате fileid:pagenumber.<br /><br /> TAB: сведения не предоставлены, так как таблица уже определена в столбце **objID** .<br /><br /> DB: сведения не предоставлены, так как база данных уже определена в столбце **DBID** .<br /><br /> Файлы. идентификатор файла, который соответствует столбцу **file_id** в представлении каталога **sys.database_files** .<br /><br /> Приложение: идентификатор, уникальный для блокируемого ресурса приложения. В формате ДбпринЦиплеид: \<first two to 16 characters of the resource string> \<hashed value> .<br /><br /> MD: зависит от типа ресурса. Дополнительные сведения см. в описании столбца **resource_description** в [sys.dm_tran_locks &#40;&#41;Transact-SQL](../../relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql.md).<br /><br /> ХБТ: сведения не предоставлены. Вместо этого используйте динамическое административное представление **sys.dm_tran_locks** .<br /><br /> AU: сведения не предоставлены. Вместо этого используйте динамическое административное представление **sys.dm_tran_locks** .|  
|**Режим**|**nvarchar (8)**|Запрашиваемый режим блокировки. Возможны следующие варианты:<br /><br /> NULL = Блокировки нет. Играет роль заполнителя.<br /><br /> Sch-S = Блокировка стабильности схемы. Заверяет, что элемент схемы, такой как таблица или индекс, не будет удален до тех пор, пока сеанс связи удерживает блокировку стабильности схемы на данный элемент схемы.<br /><br /> Sch-М = Блокировка изменения схемы. Должен поддерживаться любым сеансом связи, во время которого предполагается изменить схему данного ресурса. Заверяет, что другие сеансы не имеют ссылок на обозначенный объект.<br /><br /> S = Коллективная блокировка. Удерживающему сеансу предоставлен коллективный доступ к ресурсу.<br /><br /> U = Блокировка обновления. Указывает блокировку обновления, полученную на ресурсы, которые со временем могут быть обновлены. Используется для предотвращения общей формы взаимоблокировки, которая возникает, когда множество сеансов блокируют ресурсы для потенциального обновления в последующее время;<br /><br /> X = Монопольная блокировка. Удерживающему сеансу предоставлен исключительный доступ к ресурсу.<br /><br /> IS = Блокировка с намерением коллективного доступа. Указывает намерение поместить блокировки типа S на некоторые подчиненные ресурсы в иерархии блокировок.<br /><br /> IU = Блокировка с намерением обновления. Указывает намерение поместить блокировки типа U на некоторые подчиненные ресурсы в иерархии блокировок.<br /><br /> IX = Блокировка с намерением монопольного доступа. Указывает намерение поместить блокировки типа X на некоторые подчиненные ресурсы в иерархии блокировок.<br /><br /> SIU = Коллективная блокировка с намерением обновления. Указывает коллективный доступ к ресурсу с намерением получения блокировок обновления на подчиненные ресурсы в иерархии блокировок.<br /><br /> SIX = Коллективная блокировка с намерением монопольного доступа. Указывает коллективный доступ к ресурсу с намерением получения монопольных блокировок на подчиненные ресурсы в иерархии блокировок.<br /><br /> UIX = Блокировка обновления с намерением монопольного доступа. Указывает блокировку обновления ресурса с намерением получения монопольных блокировок на подчиненные ресурсы в иерархии блокировок.<br /><br /> BU = Блокировка массового обновления. Используется для массовых операций.<br /><br /> RangeS_S = Блокировка разделяемого диапазона ключей и разделяемых ресурсов. Указывает на последовательный просмотр диапазона.<br /><br /> RangeS_U = Блокировка разделяемого диапазона ключей и обновляемых ресурсов. Указывает на последовательное сканирование обновления.<br /><br /> RangeI_N = Блокировка вставляемого диапазона ключей и NULL-ресурсов. Используется для проверки диапазонов, перед тем как вставить новый ключ в индекс.<br /><br /> RangeI_S = блокировка преобразования диапазона ключей. Создается перекрытием блокировок RangeI_N и S;<br /><br /> RangeI_U = Блокировка преобразования диапазона ключей, созданная перекрытием блокировок RangeI_N и U;<br /><br /> RangeI_X = Блокировка преобразования диапазона ключей, созданная перекрытием блокировок RangeI_N и X;<br /><br /> RangeX_S = блокировка преобразования диапазона ключей, созданная перекрытием блокировок RangeI_N и RangeS_S.<br /><br /> RangeX_U = Блокировка преобразования диапазона ключей, созданная перекрытием блокировок RangeI_N и RangeS_U.<br /><br /> RangeX_X = Блокировка монопольного диапазона ключей и монопольных ресурсов. Блокировка диалога, используемая во время обновления ключа в диапазоне.|  
|**Состояние**|**nvarchar (5)**|Состояние запроса блокировки:<br /><br /> КНВРТ: блокировка преобразуется из другого режима, но преобразование блокируется другим процессом, удерживающим блокировку с конфликтующим режимом.<br /><br /> GRANT: блокировка получена.<br /><br /> WAIT: Блокировка заблокирована другим процессом, удерживающим блокировку с конфликтующим режимом.|  
  
## <a name="remarks"></a>Замечания  
 Пользователи могут управлять блокировкой операций чтения следующим образом.  
  
-   Используя SET TRANSACTION ISOLATION LEVEL для указания уровня блокировки для сеанса. Синтаксис и ограничения см. в разделе [SET TRANSACTION изоляцией LEVEL &#40;Transact-SQL&#41;](../../t-sql/statements/set-transaction-isolation-level-transact-sql.md).  
  
-   Использование табличных указаний блокировки, чтобы задать уровень блокировки для индивидуальной ссылки на таблицу в предложении FROM. Синтаксис и ограничения см. в разделе [Табличные указания &#40;Transact-SQL&#41;](../../t-sql/queries/hints-transact-sql-table.md).  
  
 Все распределенные транзакции, не связанные с сеансом, являются потерянными транзакциями. Компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] назначает всем потерянным транзакциям значение SPID равное -2, что упрощает выявление блокирующих распределенных транзакций. Дополнительные сведения см. в статье [Использование помеченных транзакций для согласованного восстановления связанных баз данных (модель полного восстановления)](../../relational-databases/backup-restore/use-marked-transactions-to-recover-related-databases-consistently.md).  
  
## <a name="permissions"></a>Разрешения  
 Необходимо разрешение VIEW SERVER STATE.  
  
## <a name="examples"></a>Примеры  
  
### <a name="a-listing-all-locks"></a>A. Перечисление всех блокировок  
 В следующем примере отображаются сведения обо всех блокировках, которые в данный момент удерживаются экземпляром компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
```sql  
USE master;  
GO  
EXEC sp_lock;  
GO  
```  
  
### <a name="b-listing-a-lock-from-a-single-server-process"></a>Б. Перечисление блокировок от односерверного процесса  
 В следующем примере отображаются сведения о процессе с идентификатором `53`, включая его блокировки.  
  
```sql  
USE master;  
GO  
EXEC sp_lock 53;  
GO  
```  
  
## <a name="see-also"></a>См. также:  
 [sys.dm_tran_locks (Transact-SQL)](../../relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql.md)   
 [DB_NAME (Transact-SQL)](../../t-sql/functions/db-name-transact-sql.md)   
 [KILL (Transact-SQL)](../../t-sql/language-elements/kill-transact-sql.md)   
 [OBJECT_NAME (Transact-SQL)](../../t-sql/functions/object-name-transact-sql.md)   
 [sp_who (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-who-transact-sql.md)   
 [sys.database_files (Transact-SQL)](../../relational-databases/system-catalog-views/sys-database-files-transact-sql.md)   
 [sys.dm_os_tasks &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-os-tasks-transact-sql.md)   
 [sys.dm_os_threads (Transact-SQL)](../../relational-databases/system-dynamic-management-views/sys-dm-os-threads-transact-sql.md)  
  
  
