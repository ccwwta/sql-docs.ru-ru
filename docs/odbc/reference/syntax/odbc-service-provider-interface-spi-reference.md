---
description: Справочник по интерфейсу службы доступа (SPI) ODBC
title: Справочник по интерфейсу поставщика служб ODBC (SPI) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.assetid: cdeffb4a-f344-4abe-97f3-be2ede1c8e59
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: e4cbf20ed3d158fca4e7ae58854bf53778dc9db6
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99174626"
---
# <a name="odbc-service-provider-interface-spi-reference"></a>Справочник по интерфейсу службы доступа (SPI) ODBC
Обычно ODBC определяет интерфейс программирования приложений (API). Функции в API могут вызываться приложениями и должны быть реализованы в диспетчере драйверов и драйвере.  
  
 С добавлением функции пулов соединений с учетом драйверов ODBC вводит интерфейс поставщика услуг (SPI). Функции в индексе SPI используются для обмена данными между диспетчером драйверов и драйвером. Функции SPI реализуются драйвером. Диспетчер драйверов не предоставляет приложениям функции SPI. Приложения не должны вызывать эти функции напрямую.  
  
 Включите склспи. h для разработки драйвера ODBC.  
  
 Этот раздел содержит следующие подразделы.  
  
-   [склклеанупконнектионпулид](../../../odbc/reference/syntax/sqlcleanupconnectionpoolid-function.md)  
  
-   [склжетпулид](../../../odbc/reference/syntax/sqlgetpoolid-function.md)  
  
-   [склпулконнект](../../../odbc/reference/syntax/sqlpoolconnect-function.md)  
  
-   [склратеконнектион](../../../odbc/reference/syntax/sqlrateconnection-function.md)  
  
-   [склсетконнектаттрфордбЦинфо](../../../odbc/reference/syntax/sqlsetconnectattrfordbcinfo-function.md)  
  
-   [склсетконнектинфо](../../../odbc/reference/syntax/sqlsetconnectinfo-function.md)  
  
-   [склсетдриверконнектинфо](../../../odbc/reference/syntax/installation-and-configuration-wwi-oltp.md)  
  
## <a name="see-also"></a>См. также:  
 [Разработка драйвера ODBC](../../../odbc/reference/develop-driver/developing-an-odbc-driver.md)   
 [Разработка Connection-Pool осведомленности в драйвере ODBC](../../../odbc/reference/develop-driver/developing-connection-pool-awareness-in-an-odbc-driver.md)   
 [Организация пулов соединений диспетчера драйверов](../../../odbc/reference/develop-app/driver-manager-connection-pooling.md)
