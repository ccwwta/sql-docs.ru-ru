---
description: MSSQLSERVER_18452
title: MSSQLSERVER_18452 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 18456 (Database Engine error)
- 18452 (Database Engine error)
ms.assetid: 21da332c-e81d-4dee-a9d2-95598911b3be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6bdfef25fcb7c159c22355d173182cc077d9b3a8
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99196525"
---
# <a name="mssqlserver_18452"></a>MSSQLSERVER_18452
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|18452|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|LOGON_INVALID_CONNECT|  
|Текст сообщения|Ошибка входа пользователя «%.*ls». Данное имя входа является именем входа SQL Server и не может использоваться для аутентификации Windows.%.\*ls|  
  
## <a name="explanation"></a>Объяснение  
Пользователь попытался выполнить вход с учетными данными, правильность которых нельзя проверить. Возможные причины.  
  
-   Имя входа может быть именем входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], но сервер допускает только проверку подлинности Windows.  
  
-   Попытка подключения с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], но использованное имя входа не существует в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
-   Процедура входа может использовать проверку подлинности Windows, но имя входа — неопознанный участник Windows. Неопознанный участник Windows означает, что имя входа не может быть проверено Windows. Причина может быть в том, что имя входа Windows принадлежит домену, который не является доверенным.  
  
Аналогичные неполадки могут вызвать менее определенную ошибку 18456.  
  
## <a name="user-action"></a>Действие пользователя  
При попытке подключения с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] убедитесь, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] настроен в режиме смешанной проверки подлинности.  
  
При попытке подключения с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] убедитесь, что имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] существует.  
  
При попытке подключения с использованием проверки подлинности Windows убедитесь, что выполнен правильный вход в нужный домен.  
  
