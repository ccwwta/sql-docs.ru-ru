---
description: Ошибки (ADO)
title: Ошибки (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- OLE DB providers [ADO]
- ADO, OLE DB providers
ms.assetid: 8ae6611b-3069-4155-b014-c0c9da37be39
author: rothja
ms.author: jroth
ms.openlocfilehash: b26899566d428a1b04c918c2552972448d996597
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100037514"
---
# <a name="errors-ado"></a>Ошибки (ADO)
Любая операция, включающая объекты ADO, может формировать одну или несколько ошибок поставщика. При возникновении каждой ошибки в коллекцию **ошибок** объекта **Connection** помещаются один или несколько объектов **ошибок** . Дополнительные сведения об обработке предупреждений и ошибок в приложении ADO см. в разделе [Обработка ошибок](./error-handling.md).  
  
 Ошибки приложения могут вызываться отдельным механизмом. Например, в Visual Basic объект **Err** будет содержать ошибки уровня приложения.