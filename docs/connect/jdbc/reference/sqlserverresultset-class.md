---
description: Класс SQLServerResultSet
title: Класс SQLServerResultSet | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: eaffcff1-286c-459f-83da-3150778480c9
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 729293afce0e8b6057e3348ea3d72e409a0cba1e
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99179899"
---
# <a name="sqlserverresultset-class"></a>Класс SQLServerResultSet
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Представляет результирующий набор JDBC.  
  
 **Пакет:** com.microsoft.sqlserver.jdbc  
  
 **Реализует:** [ISQLServerResultSet](../../../connect/jdbc/reference/isqlserverresultset-interface.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public final class SQLServerResultSet  
```  
  
## <a name="remarks"></a>Remarks  
 Существует два типа результирующих наборов: на стороне клиента и на стороне сервера.  
  
 Результирующие наборы на стороне клиента используются в случае, если результаты могут быть размещены в памяти клиента. Эти результаты обеспечивают наибольшую производительность и полностью считываются драйвером [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] из базы данных. Эти результирующие наборы не вводят дополнительную нагрузку на базу данных, вызываемой в результате создания курсоров на стороне сервера. Однако данные типы результирующих наборов нельзя обновлять.  
  
 Результирующие наборы на стороне сервера используются в случае, если результаты не могут быть размещены в памяти клиента или существует необходимость обновления результирующего набора. Для данного типа результирующего набора драйвер JDBC создает курсор на стороне сервера и, незаметно для пользователя, извлекает строки результирующего набора по мере того, как он выполняет прокрутку результатов.  
  
 Класс SQLServerResultSet предоставляет множество методов, которые позволяют обновить результирующий набор с помощью всех собственных типов данных Java и многих типов объектов Java.  
  
 Этот класс поддерживает распаковку в класс SQLServerResultSet, интерфейс ISQLServerResultSet и интерфейс Java.SQL.Result. См. сведения об [интерфейсах и программах-оболочках](../../../connect/jdbc/wrappers-and-interfaces.md).  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Справка по API драйвера JDBC](../../../connect/jdbc/reference/jdbc-driver-api-reference.md)  
  
  
