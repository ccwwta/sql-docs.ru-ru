---
description: MSSQLSERVER_33081
title: MSSQLSERVER_33081 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 33081 (Database Engine error)
ms.assetid: 839705e7-fa37-4c0d-9f3f-95a9eab98bcf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8be9f2bec59b51f75a7832768663535175946f60
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99208417"
---
# <a name="mssqlserver_33081"></a>MSSQLSERVER_33081
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|33081|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|SEC_DLL_TRUST_VERIFICATION_FAILED|  
|Текст сообщения|Не удалось загрузить поставщик служб шифрования "%.*ls" из-за недействительной подписи Authenticode или недействительного пути к файлу.  Проверьте наличие других ошибок в предыдущих сообщениях.|  
  
## <a name="explanation"></a>Объяснение  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не смог загрузить поставщик служб шифрования, указанный в сообщении об ошибке. Существует несколько ошибок Win API, которые могут вызвать эту ошибку. Кольцевой буфер содержит имя ошибочного API и код ошибки Windows, возвращенный API. Чтобы получить дополнительные сведения, выполните следующий запрос к представлению sys.dm_os_ring_buffers.  
  
```  
SELECT * FROM sys.dm_os_ring_buffers   
WHERE ring_buffer_type = 'RING_BUFFER_SECURITY_ERROR';  
```  
  
## <a name="user-action"></a>Действие пользователя  
Чтобы исследовать эту проблему, выполните поиск кода ошибки Windows в MSDN (https://msdn.microsoft.com/). Устраните ошибку или обратитесь к службу поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] за дополнительными сведениями. Перед обращением в службу поддержки пользователей соберите следующие данные.  
  
-   Журнал ошибок, отображающий ошибку загрузки поставщика служб шифрования.  
  
-   Выход из следующей инструкции:  
  
    ```  
    SELECT * FROM sys.dm_os_ring_buffers   
    WHERE ring_buffer_type = 'RING_BUFFER_SECURITY_ERROR';  
    ```  
  
> [!NOTE]  
> Попробуйте сразу собрать данные кольцевого буфера, поскольку они могут быть потеряны при перезагрузке.  
  
