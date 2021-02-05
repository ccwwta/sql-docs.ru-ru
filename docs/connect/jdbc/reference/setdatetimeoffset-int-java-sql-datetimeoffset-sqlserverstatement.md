---
description: Метод setDateTimeOffset(int, java.sql.DateTimeOffset) (SQLServerStatement)
title: setDateTimeOffset (int, java.sql.DateTimeOffset) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: e8b6e380-6b53-489b-be73-73fcb5258269
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 58ee3ec9304023f459a0164ecf15316ff629d308
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99179028"
---
# <a name="setdatetimeoffsetint-javasqldatetimeoffset-sqlserverstatement"></a>Метод setDateTimeOffset(int, java.sql.DateTimeOffset) (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Устанавливает указанный параметр в заданное значение типа DateTimeOffset.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public void setDateTimeOffset(int parameterIndex, DateTimeOffset dateTime)  
```  
  
#### <a name="parameters"></a>Параметры  
 *parameterIndex*  
  
 Индекс задаваемого столбца.  
  
 *dateTimeOffset*  
  
 Объект DateTimeOffset.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 DateTimeOffset имеет формат «ГГГГ-ММ-ДД ЧЧ-ММ-СС[.ннннннн] [+][-] ЧЧ:ММ». Следующая таблица приводится в справочных целях.  
  
|Тип SQL|Вставить|  
|--------------|------------|  
|DATETIME|Могут вставляться только значения в формате «ГГГГ-ММ-ДД чч:мм:сс[.ннн]»|  
|smalldatetime|Могут вставляться только значения в формате «ГГГГ-ММ-ДД чч:мм:сс»|  
|время;|Могут вставляться только значения в формате «чч:мм:сс[.ннннннн]»|  
|Дата|Могут вставляться только значения в формате «ГГГГ-ММ-ДД»|  
|datetime2|Могут вставляться только значения в формате «ГГГГ-ММ-ДД чч:мм:сс[.ннннннн]»|  
  
## <a name="see-also"></a>См. также:  
 [getDateTimeOffset (SQLServerResultSet)](../../../connect/jdbc/reference/getdatetimeoffset-sqlserverresultset.md)   
 [Элементы SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [Класс SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
