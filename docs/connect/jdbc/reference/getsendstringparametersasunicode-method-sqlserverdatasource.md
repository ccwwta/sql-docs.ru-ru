---
description: Метод getSendStringParametersAsUnicode (SQLServerDataSource)
title: Метод getSendStringParametersAsUnicode (SQLServerDataSource) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLServerDataSource.getSendStringParametersAsUnicode
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 3836d0ab-c3fb-41ff-bb89-10389594ae51
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 2bcac762b3874fd95fd03286d1a52a5654d31228
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99162311"
---
# <a name="getsendstringparametersasunicode-method-sqlserverdatasource"></a>Метод getSendStringParametersAsUnicode (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Возвращение значения **boolean**, указывающего, разрешена ли отправка параметров на сервер в Юникоде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public boolean getSendStringParametersAsUnicode()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если строковые параметры отправляются на сервер в Юникоде. В противном случае — **false**.  
  
## <a name="remarks"></a>Remarks  
 Если свойство sendStringParametersAsUnicode имеет значение **true** (значение по умолчанию), то строковые параметры отправляются на сервер в Юникоде. Если для свойства sendStringParametersAsUnicode задано значение **false**, то строковые параметры отправляются в формате ASCII/MBCS, а не в Юникоде. Если свойство sendStringParametersAsUnicode не задано, getSendStringParametersAsUnicode возвращает **true**.  
  
 Дополнительные сведения о свойстве подключения sendStringParametersAsUnicode см. в статье [Настройка свойств подключения](../../../connect/jdbc/setting-the-connection-properties.md).  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Класс SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
