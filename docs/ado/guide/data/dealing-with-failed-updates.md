---
description: Работа с ошибками обновлений
title: Работа с неудачными обновлениями | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- updates [ADO], dealing with failed updates
ms.assetid: 299c37bd-19ff-4261-8571-b9665687e075
author: rothja
ms.author: jroth
ms.openlocfilehash: a5ce736c8dd24f2398d7c8c374be260080c32e11
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100037644"
---
# <a name="dealing-with-failed-updates"></a>Работа с ошибками обновлений
Когда обновление завершается с ошибками, способ устранения ошибок зависит от природы и серьезности ошибок и логики приложения. Однако если база данных используется совместно с другими пользователями, то типичная ошибка заключается в том, что другой пользователь изменяет поле до того, как это сделано. Этот тип ошибки называется конфликтом. ADO обнаруживает эту ситуацию и сообщает об ошибке.  
  
## <a name="remarks"></a>Remarks  
 При наличии ошибок обновления они будут перехвачены в подпрограммы обработки ошибок. Отфильтруйте набор записей с помощью константы Адфилтерконфликтингрекордс, чтобы отображались только конфликтующие строки. В этом примере стратегия разрешения ошибок — это просто печать первого и последнего имени автора (au_fname и au_lname).  
  
 Код для оповещения пользователя о конфликте обновлений выглядит следующим образом:  
  
```  
objRs.Filter = adFilterConflictingRecords  
objRs.MoveFirst  
Do While Not objRst.EOF  
   Debug.Print "Conflict: Name =  "; objRs!au_fname; " "; objRs!au_lname  
   objRs.MoveNext  
Loop  
```  
  
## <a name="see-also"></a>См. также:  
 [Пакетный режим](./batch-mode.md)