---
title: пространство имен-URI-from-QName (XQuery) | Документация Майкрософт
description: Узнайте, как использовать функцию Namespace-URI-from-QName для получения URI пространства имен QName.
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: sql
ms.reviewer: ''
ms.technology: xml
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- fn:namespace-uri-from-QName function
- namespace-uri-from-QName function
ms.assetid: 4ab3f003-2a3b-4268-9e88-b615e35701b2
author: rothja
ms.author: jroth
ms.openlocfilehash: 91fc5595dadad3a3cf4c8d95c4db1da5406a968f
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100335868"
---
# <a name="functions-related-to-qnames---namespace-uri-from-qname"></a>Функции, связанные с QName — namespace-uri-from-QName
[!INCLUDE [SQL Server Azure SQL Database ](../includes/applies-to-version/sqlserver.md)]

  Возвращает строку, представляющую URI пространства имен QName, заданного *$arg*. Результатом является пустая последовательность, если *$arg* является пустой последовательностью.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace-uri-from-QName($arg as xs:QName?) as xs:string?  
```  
  
## <a name="arguments"></a>Аргументы  
 *$arg*  
 QName, для которого возвращается URI-код пространство имен.  
  
## <a name="examples"></a>Примеры  
 В этом разделе приведены примеры запросов XQuery к экземплярам XML, хранящимся в различных столбцах типа **XML** в базе данных AdventureWorks.  
  
### <a name="a-retrieve-the-namespace-uri-from-a-qname"></a>A. Получение URI-адреса пространства имен из QName  
 Рабочий пример см. в разделе [local-name-from-QName &#40;XQuery&#41;](../xquery/functions-related-to-qnames-local-name-from-qname.md).  
  
### <a name="implementation-limitations"></a>Ограничения реализации  
 Существуют следующие ограничения:  
  
-   Функция **Namespace-URI-from-QName ()** возвращает экземпляры xs: String вместо xs: anyURI.  
  
## <a name="see-also"></a>См. также:  
 [Функции, связанные с QName &#40;XQuery&#41;](./functions-related-to-qnames-expanded-qname.md)  
  
