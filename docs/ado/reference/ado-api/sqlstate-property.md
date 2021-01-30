---
description: Свойство SQLState
title: Свойство SQLState | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Error::GetSQLState
- Error::SQLState
- Error::get_SQLState
helpviewer_keywords:
- SQLState property
ms.assetid: f9e25967-54b0-444d-af2a-0d2c75365d3e
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ebacade44d53ddf142f22f9e30bce140e375592
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99170216"
---
# <a name="sqlstate-property"></a>Свойство SQLState
Указывает состояние SQL для данного объекта [ошибки](./error-object.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает **строковое** значение из пяти символов, следующее за стандартом ANSI SQL, и указывает код ошибки.  
  
## <a name="remarks"></a>Замечания  
 Используйте свойство **SQLSTATE** для чтения кода ошибки из пяти символов, возвращаемого поставщиком при возникновении ошибки во время обработки инструкции SQL. Например, при использовании поставщика Microsoft OLE DB для ODBC с базой данных Microsoft SQL Server коды ошибок состояния SQL исходят из ODBC, основываясь на ошибках ODBC или об ошибках, происходящих в Microsoft SQL Server, а затем сопоставленных ошибкам ODBC. Эти коды ошибок описаны в стандарте ANSI SQL, но могут быть реализованы по-разному в разных источниках данных.  
  
## <a name="applies-to"></a>Применение  
 [Объект Error](./error-object.md)  
  
## <a name="see-also"></a>См. также:  
 [Примеры свойств Description, HelpContext, HelpFile, NativeError, Number, Source и SQLState (Visual Basic)](./description-helpcontext-helpfile-nativeerror-number-source-example-vb.md)   
 [Примеры свойств Description, HelpContext, HelpFile, NativeError, Number, Source и SQLState (Visual c++)](./description-helpcontext-helpfile-nativeerror-number-source-example-vc.md)