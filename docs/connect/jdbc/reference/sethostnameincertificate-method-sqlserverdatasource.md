---
description: Метод setHostNameInCertificate (SQLServerDataSource)
title: Метод setHostNameInCertificate (SQLServerDataSource) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- setHostNameInCertificate Method (SQLServerDataSource)
apilocation:
- setHostNameInCertificate Method (SQLServerDataSource)
apitype: Assembly
ms.assetid: 2bcf4f2e-a103-4374-abc4-ffad4ce8e3c0
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 37405a18c794b1fa7cbddf0fdaed92a4727f9907
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99178972"
---
# <a name="sethostnameincertificate-method-sqlserverdatasource"></a>Метод setHostNameInCertificate (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Задает имя узла, используемого для проверки TLS-сертификата [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], который ранее назывался SSL-сертификатом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public void setHostNameInCertificate(java.lang.String hostNameInCertificate)  
```  
  
#### <a name="parameters"></a>Параметры  
 *hostNameInCertificate*  
  
 Значение типа **String**, содержащее имя узла.  
  
## <a name="remarks"></a>Remarks  
 Значение hostNameInCertificate используется для проверки TLS/SSL-сертификата [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] при использовании шифрования TLS для уровня связи. По умолчанию используется значение NULL.  
  
 Если свойство hostNameInCertificate имеет значение NULL или оно не указано, то [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] использует значение свойства serverName для проверки по TLS/SSL-сертификату [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Если для свойства hostNameInCertificate задано строковое значение или пустая строка "", драйвер использует это значение для проверки TLS/SSL-сертификата сервера.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Класс SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
