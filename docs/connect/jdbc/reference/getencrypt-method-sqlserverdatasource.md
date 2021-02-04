---
description: Метод getEncrypt (SQLServerDataSource)
title: Метод getEncrypt (SQLServerDataSource) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- getEncrypt Method (SQLServerDataSource)
apilocation:
- getEncrypt Method (SQLServerDataSource)
apitype: Assembly
ms.assetid: 1cdb12dd-6e6f-4bbd-8f5f-9e630f3ee2c9
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: b9bbcb5adb686825132b2ae166beecd5846693f9
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99175854"
---
# <a name="getencrypt-method-sqlserverdatasource"></a>Метод getEncrypt (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Задает значение типа **Boolean**, определяющее, включено ли свойство encrypt.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public boolean getEncypt()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если шифрование включено. В противном случае — **false**.  
  
## <a name="remarks"></a>Remarks  
 Если для свойства encrypt задано значение **true**, то [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] обеспечивает в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] шифрование TLS всех данных, передаваемых между клиентом и сервером при условии, что на сервере установлен сертификат.  
  
 Если свойство encrypt не указано или имеет значение **false**, то драйвер не будет принудительно применять в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] поддержку шифрования TLS. Если в экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] не настроено принудительное шифрование TLS, то подключение устанавливается без применения шифрования. Если в экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] настроено принудительное шифрование TLS, [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] автоматически включит шифрование TLS при запуске на корректно настроенной виртуальной машине Java (JVM). В противном случае соединение будет прервано, а драйвер выдаст ошибку. Если свойство шифрования не задано, метод [getEncrypt](../../../connect/jdbc/reference/getencrypt-method-sqlserverdatasource.md) возвращает значение по умолчанию **false**.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Класс SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
