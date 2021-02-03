---
description: MSSQLSERVER_26014
title: MSSQLSERVER_26014 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 26014 (Database Engine error)
ms.assetid: e2b0dfc7-0681-4e5d-8875-1d5f63534086
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f179b8ecef4e2c80a045b858ca60539374260cbd
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99198209"
---
# <a name="mssqlserver_26014"></a>MSSQLSERVER_26014
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|26014|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|SNI_SSL_USER_CERT_FAILURE|  
|Текст сообщения|Не удалось загрузить указанный пользователем сертификат [Cert Hash(sha1) "%hs"]. Сервер не будет принимать соединения. Убедитесь в том, что сертификат установлен правильно. См. раздел «Настройка сертификата для использования протоколом SSL» в электронной документации.|  
  
## <a name="explanation"></a>Объяснение  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] попытался загрузить сертификат, указанный в сообщении, но эта операция окончилась неудачей. Необходимо устранить эту проблему, прежде чем использовать этот сертификат в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
Возможны следующие причины ошибки.  
  
-   Сертификат перемещен или удален.  
  
-   Изменилось имя входа, используемое в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], и [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не имеет разрешения для доступа к сертификату.  
  
-   Истек срок действия сертификата.  
  
## <a name="user-action"></a>Действие пользователя  
Убедитесь, что сертификат, указанный в сообщении, существует в системе, является доступным и допустимым для использования.  
  
