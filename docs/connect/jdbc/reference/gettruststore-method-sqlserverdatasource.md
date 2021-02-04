---
description: Метод getTrustStore (SQLServerDataSource)
title: Метод getTrustStore (SQLServerDataSource) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- getTrustStore Method (SQLServerDataSource)
apilocation:
- getTrustStore Method (SQLServerDataSource)
apitype: Assembly
ms.assetid: 8f5850e4-8627-49a8-ba0e-b1f4014322a5
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 71365a85690c74025b6d807eb4def767156996cd
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99165472"
---
# <a name="gettruststore-method-sqlserverdatasource"></a>Метод getTrustStore (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращает путь к файлу сертификата trustStore (включая имя файла).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public java.lang.String getTrustStore()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение типа **String**, содержащее путь к файлу сертификата trustStore (включая имя файла), или значение NULL, если значение не задано.  
  
## <a name="remarks"></a>Комментарии  
 Если свойство trustStore не задано, то метод [getTrustStore](../../../connect/jdbc/reference/gettruststore-method-sqlserverdatasource.md) возвращает значение NULL.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Класс SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
