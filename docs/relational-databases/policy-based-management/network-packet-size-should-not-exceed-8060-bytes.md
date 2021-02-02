---
description: Размер сетевого пакета не должен превышать 8060 байт
title: Размер сетевого пакета не должен превышать 8060 байт | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 86db5da1-afe4-4fbb-8bf8-33cedc7e4361
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 737bad4dd5994bebdf23ea8ebab5f4ed6f788266
ms.sourcegitcommit: f30b5f61c514437ea58acc5769359c33255b85b5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2021
ms.locfileid: "99076416"
---
# <a name="network-packet-size-should-not-exceed-8060-bytes"></a>Размер сетевого пакета не должен превышать 8060 байт
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  Если значение, заданное для параметра хранимой процедуры sp_configure 'network packet size', или размер пакета любого вошедшего в систему пользователя превышает 8 060 байт, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняет другие операции выделения памяти. Это может привести к увеличению виртуального адресного пространства процессов, которое не зарезервировано для буферного пула.  
  
## <a name="best-practices-recommendations"></a>Рекомендации  
 Размер сетевого пакета не должен превышать 8 060 байт.  
  
## <a name="for-more-information"></a>Дополнительные сведения см. в разделе  
 [Статья 903002 базы знаний Майкрософт](https://www.betaarchive.com/wiki/index.php?title=Microsoft_KB_Archive/903002)  
  
## <a name="see-also"></a>См. также:  
 [Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик](../../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
