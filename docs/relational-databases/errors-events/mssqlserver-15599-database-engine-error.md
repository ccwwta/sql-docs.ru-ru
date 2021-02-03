---
description: MSSQLSERVER_15599
title: MSSQLSERVER_15599 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 15599 (Database Engine error)
ms.assetid: 97e427a9-8587-46ea-954b-974b5df9c223
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f6ec0fb50ca6a4dca0970e8483e6ea1570d55d85
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99196873"
---
# <a name="mssqlserver_15599"></a>MSSQLSERVER_15599
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|15599|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|SEC_LOCAL_TEMP_AUDIT_PERMISSIONS|  
|Текст сообщения|Аудит и разрешения нельзя задать для локальных временных объектов.|  
  
## <a name="explanation"></a>Объяснение  
Аудит и разрешения не работают при установке для локальных или глобальных временных объектов. Инструкция не завершилась ошибкой (возвращен успешный код), но не имела никакого эффекта.  
  
Это поведение не изменилось, хотя, начиная с [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], это информационное сообщение предупреждает пользователя.  
  
## <a name="user-action"></a>Действие пользователя  
Действия не требуются, но подумайте над удалением инструкций, которые пытаются установить аудит или разрешения на локальных или глобальных временных объектах.  
  
