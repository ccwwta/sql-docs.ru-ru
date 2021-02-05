---
description: Метод updateBinaryStream (java.lang.String, java.io.InputStream)
title: Метод updateBinaryStream (java.io.InputStream) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: 56883144-26a0-4f45-ad36-4f616369af3e
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 9cf9c5b6047083f64dad5e029ec9f9301ef23be4
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99183281"
---
# <a name="updatebinarystream-method-javalangstring-javaioinputstream"></a>Метод updateBinaryStream (java.lang.String, java.io.InputStream)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Обновляет значение двоичного потока в указанном столбце.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public void updateBinaryStream(java.lang.String columnLabel,  
                               java.io.InputStream x)  
```  
  
#### <a name="parameters"></a>Параметры  
 *columnLabel*  
  
 Значение типа **String**, содержащее метку столбца.  
  
 *x*  
  
 Объект InputStream.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод updateBinaryStream задается с помощью метода updateBinaryStream в интерфейсе java.sql.ResultSet.  
  
 Использование этого метода при работе с типами данных SQL Server **image**, **text** и **ntext** может повлиять на производительность.  
  
 Этот метод передает байты от объекта InputStream выбранным двоичным столбцам [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], таким как binary, varbinary, varbinary(max), image, xml и udt. В этом методе не поддерживается обновление символьных столбцов. Для обновления с помощью InputStream символьных столбцов используйте метод [updateAsciiStream](../../../connect/jdbc/reference/updateasciistream-method-sqlserverresultset.md).  
  
## <a name="see-also"></a>См. также:  
 [Метод updateBinaryStream &#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/updatebinarystream-method-sqlserverresultset.md)   
 [Элементы SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Класс SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
