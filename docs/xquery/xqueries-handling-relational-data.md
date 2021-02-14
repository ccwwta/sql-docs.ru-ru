---
title: Запросы XQuery использующие обработка реляционных данных | Документация Майкрософт
description: 'Узнайте, как привязать реляционные данные, отличные от XML, к XML с помощью расширений XQuery SQL: column () и SQL: variable ().'
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: sql
ms.reviewer: ''
ms.technology: xml
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- relational data [XQuery]
- XQuery, relational data
ms.assetid: 9812b71a-52ec-48a0-92f3-016a93660229
author: rothja
ms.author: jroth
ms.openlocfilehash: cadad1b4db6a0f0a6284ecb4beb6eadba9e59adc
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100344956"
---
# <a name="xqueries-handling-relational-data"></a>Запросы XQuery, обрабатывающие реляционные данные
[!INCLUDE [SQL Server Azure SQL Database ](../includes/applies-to-version/sqlserver.md)]

  Запрос XQuery указывается для столбца или переменной типа **XML** с помощью одного из [методов типа данных XML](../t-sql/xml/xml-data-type-methods.md). К ним относятся **запрос ()**, **значение ()**, **exist ()** или **Modify ()**. Запрос XQuery выполняется для экземпляра XML, указанного в запросе, создающем XML-код.  
  
 XML-код, созданный в результате выполнения запроса XQuery, может включать значения, полученные от других переменных Transact-SQL или столбцов набора строк. Для связи реляционных данных в формате, отличном от XML, с итоговым XML-кодом в SQL Server в форме расширений XQuery реализованы следующие псевдофункции:  
  
-   Функция **SQL: column ()**  
  
-   Функция **SQL: variable ()**  
  
 Эти расширения XQuery можно использовать при указании запроса XQuery в методе **query ()** типа данных **XML** . В результате метод **query ()** может формировать XML, объединяющий данные из типов данных XML и не **XML** .  
  
 Эти функции также можно использовать при использовании методов типа данных **XML** **Modify ()**, **value ()**, **query ()** и **exist ()** для предоставления реляционного значения внутри XML.  
  
 Дополнительные сведения см. в разделе [функции SQL: column () (XQuery)](../xquery/xquery-extension-functions-sql-column.md) и [SQL: variable () (XQuery)](../xquery/xquery-extension-functions-sql-variable.md).  
  
## <a name="see-also"></a>См. также:  
 [Данные XML (SQL Server)](../relational-databases/xml/xml-data-sql-server.md)   
 [Справочник по языку XQuery (SQL Server)](../xquery/xquery-language-reference-sql-server.md)   
 [Создание XML &#40;XQuery&#41;](../xquery/xml-construction-xquery.md)  
  
  
