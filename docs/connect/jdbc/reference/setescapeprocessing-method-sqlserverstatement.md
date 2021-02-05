---
description: Метод setEscapeProcessing (SQLServerStatement)
title: Метод setEscapeProcessing (SQLServerStatement) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerStatement.setEscapeProcessing
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 6ac0682e-e04c-4fdb-893b-92408d42051e
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: c60d547ed0a72a573bda8f16b4051ff796261dd5
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99173460"
---
# <a name="setescapeprocessing-method-sqlserverstatement"></a>Метод setEscapeProcessing (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Задается режим обработки escape-последовательностей.  
  
> [!NOTE]  
>  Для [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] обработка escape-последовательностей всегда включена. Если установить значение false в этом методе, обработка останется включенной.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public final void setEscapeProcessing(boolean enable)  
```  
  
#### <a name="parameters"></a>Параметры  
 *enable*  
  
 Значение **true**, чтобы включить обработку escape-последовательностей. В противном случае — **false**.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод setEscapeProcessing задается с помощью метода setEscapeProcessing в интерфейсе java.sql.Statement.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [Класс SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
