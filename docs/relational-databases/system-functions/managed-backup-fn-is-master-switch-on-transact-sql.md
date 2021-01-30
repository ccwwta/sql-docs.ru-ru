---
description: managed_backup.fn_is_master_switch_on managed_backup (Transact-SQL)
title: managed_backup managed_backup.fn_is_master_switch_on (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- fn_is_master_switch_on
- fn_is_master_switch_on_TSQL
- smart_admin.fn_is_master_switch_on
- smart_admin.fn_is_master_switch_on_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- smart_admin.fn_is_master_switch_on
- fn_is_master_switch_on
ms.assetid: e8c2108d-b104-46cb-9645-a15f46112c86
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 32395235a4d644814c7ff090fd74abc9030b2eda
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99207375"
---
# <a name="managed_backupfn_is_master_switch_on-transact-sql"></a>managed_backup.fn_is_master_switch_on managed_backup (Transact-SQL)
[!INCLUDE [sqlserver2016](../../includes/applies-to-version/sqlserver2016.md)]

  Возвращает состояние операций [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] в экземпляре SQL Server.  
  
 Используйте эту функцию для получения текущего состояния [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].  
  
 
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
managed_backup.fn_is_master_switch_on ()  
```  
  
##  <a name="arguments"></a><a name="Arguments"></a> Аргументы  
 Нет  
  
## <a name="return-type"></a>Тип возвращаемых данных  
 **BIT**  
  
 1 = служба [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] активна, 0 = служба [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] приостановлена.  
  
## <a name="security"></a>Безопасность  
  
### <a name="permissions"></a>Разрешения  
 Необходимы разрешения SELECT для функции.  
  
## <a name="see-also"></a>См. также:  
 [Управляемое резервное копирование SQL Server в Microsoft Azure](../../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md)  
  
  
