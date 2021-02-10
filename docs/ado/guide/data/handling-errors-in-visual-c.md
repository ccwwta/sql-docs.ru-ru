---
description: Обработка ошибок в Visual C++
title: Обработка ошибок в Visual C++ | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- errors [ADO], Visual C++
- Visual C++ error handling [ADO]
ms.assetid: b7576f07-020a-45f7-9e79-b5756f33f7ab
author: rothja
ms.author: jroth
ms.openlocfilehash: 61435c9d66800704e962cd4a399c87e72f6558c8
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100037374"
---
# <a name="handling-errors-in-visual-c"></a>Обработка ошибок в Visual C++
В COM большинство операций возвращают код возврата HRESULT, указывающий, успешно ли завершилась функция. Директива #import создает код-оболочку вокруг каждого "необработанного" метода или свойства и проверяет возвращенное значение HRESULT. Если HRESULT указывает на сбой, код программы-оболочки вызывает ошибку COM путем вызова _com_issue_errorex () с кодом возврата HRESULT в качестве аргумента. Объекты ошибок COM могут быть перехвачены в блок **try-catch** . (Для повышения эффективности перехватите ссылку на объект _com_error.)  
  
 Помните, что это ошибки ADO: они вызваны сбоем операции ADO. Ошибки, возвращенные базовым поставщиком, отображаются как объекты **ошибок** в коллекции **ошибок** объекта **Connection** .  
  
 Директива #import создает только подпрограммы обработки ошибок для методов и свойств, объявленных в ADO. dll. Тем не менее можно воспользоваться тем же механизмом обработки ошибок, создав собственный макрос проверки ошибок или встроенную функцию. Примеры см. в разделе Visual C++ расширений®.
