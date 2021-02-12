---
description: Удаление компонентов SSMA для MySQL (MySQLToSql)
title: Удаление SSMA для компонентов MySQL (MySQLToSql) | Документация Майкрософт
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Uninstalling, Extension pack
- Uninstalling, SSMA for MySQL client
ms.assetid: 87cdbd49-a0c9-4b00-8a93-34188b18d11a
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: 898b55146317a09b43b1b4df63a22a9a74882ee9
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100074645"
---
# <a name="removing-the-ssma-for-mysql-components-mysqltosql"></a>Удаление компонентов SSMA для MySQL (MySQLToSql)
После завершения миграции баз данных из MySQL в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может потребоваться удалить компоненты SSMA. Вы можете удалить клиентские компоненты в любое время. Однако если удалить пакет расширений из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , SSMA больше не будет поддерживать перенос данных из MySQL в целевую базу данных (SQL Server и SQL Azure) с помощью Server-Side механизма миграции данных.  
  
## <a name="uninstalling-the-ssma-for-mysql-client"></a>Удаление клиента SSMA для MySQL  
Удалить SSMA можно с помощью компонента " **Установка и удаление программ**".  
  
**Удаление SSMA**  
  
1.  На панели управления и откройте элемент **Установка и удаление программ**.  
  
2.  Выберите **Помощник по миграции Microsoft SQL Server для MySQL**, а затем нажмите кнопку **Удалить**.  
  
3.  Чтобы подтвердить удаление SSMA, нажмите кнопку **Да**.  
  
## <a name="uninstalling-the-extension-pack"></a>Удаление пакета расширений  
Удалить пакет расширений можно с помощью компонента " **Установка и удаление программ**".  
  
**Удаление пакета расширений**  
  
1.  На панели управления и откройте элемент **Установка и удаление программ**.  
  
2.  Выберите **Помощник по миграции Microsoft SQL Server для пакета расширений MySQL**, а затем нажмите кнопку **Удалить**.  
  
3.  Чтобы подтвердить удаление пакета расширений, нажмите кнопку **Да**.  
  
4.  На странице экземпляры с скриптами базы данных служебных программ выберите экземпляр и нажмите кнопку **Далее**.  
  
5.  На странице Параметры соединения выберите метод проверки подлинности и нажмите кнопку **Далее**.  
  
    При проверке подлинности Windows будут использоваться учетные данные Windows для входа на экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . При выборе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] проверки подлинности необходимо ввести [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имя входа и пароль.  
  
6.  На странице операция завершена нажмите кнопку **ОК**.  
  
7.  На странице Готово нажмите кнопку **выход**.  
  
После завершения процесса удаления можно убедиться, что объекты в схеме **sysdb.ssma_MySQL** и, возможно, вся база данных **сисдб** , были удалены с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] . Однако при использовании других продуктов SSMA они также используют базу данных **сисдб** . Если база данных существует и вы уверены, что другие базы данных не ссылаются на объекты в этой базе данных, можно отключить базу данных.  
  
## <a name="see-also"></a>См. также:  
[Установка SSMA для клиента MySQL &#40;MySQLToSQL&#41;](../../ssma/mysql/installing-ssma-for-mysql-client-mysqltosql.md)  
[Установка компонентов SSMA на SQL Server](installing-ssma-components-on-sql-server-mysqltosql.md)  
  
