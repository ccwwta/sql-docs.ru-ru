---
description: Unprepare SQL, класс событий
title: Класс событий Unprepare SQL | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- Unprepare SQL event class
ms.assetid: cfcbdd9d-d83b-46ae-9caa-d1833b5913f4
author: stevestein
ms.author: sstein
monikerRange: =azuresqldb-current||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: b5277443ad82be9f236dbedb96eb0cfe746a27ff
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99193314"
---
# <a name="unprepare-sql-event-class"></a>Unprepare SQL, класс событий
[!INCLUDE [SQL Server - ASDB](../../includes/applies-to-version/sql-asdb.md)]
  Событие класса событий Unprepare SQL указывает, что приложение, использующее технологии SqlClient, ODBC, OLE DB или DB-Library, аннулировало (удалило) подготовленную инструкцию или несколько инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] .  
  
## <a name="unprepare-sql-event-class-data-columns"></a>Столбцы данных класса событий Unprepare SQL  
  
|Имя столбца данных|Тип данных|Описание|Идентификатор столбца|Фильтруемый|  
|----------------------|---------------|-----------------|---------------|----------------|  
|ApplicationName|**nvarchar**|Имя клиентского приложения, установившего соединение с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Этот столбец заполняется значениями, передаваемыми приложением, а не отображаемым именем программы.|10|Да|  
|ClientProcessID|**int**|Идентификатор, присвоенный главным компьютером сервера процессу, в котором работает клиентское приложение. Этот столбец данных заполняется в том случае, если клиент вводит идентификатор клиентского процесса.|9|Да|  
|DatabaseID|**int**|Идентификатор базы данных, указанной в инструкции USE *database* , или базы данных по умолчанию, если для данного экземпляра инструкция USE *database* не выполнялась. [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] отображает имя базы данных, если столбец данных ServerName захвачен при трассировке и сервер доступен. Определите значение для базы данных, используя функцию DB_ID.|3|Да|  
|имя_базы_данных|**nvarchar**|Имя базы данных, в которой выполняется пользовательская инструкция.|35|Да|  
|EventClass|**int**|Тип события = 73.|27|Нет|  
|EventSequence|**int**|Последовательность данного события в запросе.|51|Нет|  
|GroupID|**int**|Идентификатор группы рабочей нагрузки, в которой запускается событие трассировки SQL.|66|Да|  
|Дескриптор|**int**|Дескриптор подготовленной инструкции Transact-SQL.|33|Да|  
|HostName|**nvarchar**|Имя компьютера, на котором выполняется клиентская программа. Заполнение этого столбца данных производится в том случае, если клиент предоставляет имя узла. Чтобы определить имя узла, используйте функцию HOST_NAME.|8|Да|  
|IsSystem|**int**|Указывает, произошло событие в системном или в пользовательском процессе. 1 = системный, 0 = пользовательский.|60|Да|  
|LoginName|**nvarchar**|Имя входа пользователя (либо имя входа безопасности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , либо учетные данные входа [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows в формате «ДОМЕН\имя_пользователя»).|11|Да|  
|LoginSid|**image**|Идентификатор безопасности вошедшего в систему пользователя. Эти сведения можно найти в каталоге sys.server_principals. Значение идентификатора безопасности уникально для каждого имени входа на сервере.|41|Да|  
|NTDomainName|**nvarchar**|Домен Windows, к которому принадлежит пользователь.|7|Да|  
|NTUserName|**nvarchar**|Имя пользователя Windows.|6|Да|  
|RequestID|**int**|Идентификатор запроса, содержащего инструкцию.|49|Да|  
|ServerName|**nvarchar**|Имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , для которого производится трассировка.|26|Нет|  
|SessionLoginName|**nvarchar**|Имя входа пользователя, создавшего этот сеанс. Например, при соединении с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] под именем Login1 и при выполнении инструкции под именем Login2 SessionLoginName будет содержать значение Login1, а LoginName — значение Login2. В этом столбце отображаются как имена входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , так и имена входа Windows.|64|Да|  
|SPID|**int**|Идентификатор сеанса, в котором произошло событие.|12|Да|  
|StartTime|**datetime**|Время начала события, если оно известно.|14|Да|  
|TransactionID|**bigint**|Назначенный системой идентификатор транзакции.|4|Да|  
|XactSequence|**bigint**|Токен, описывающий текущую транзакцию.|50|Да|  
  
## <a name="see-also"></a>См. также:  
 [Хранимая процедура sp_trace_setevent (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql.md)  
  
  
