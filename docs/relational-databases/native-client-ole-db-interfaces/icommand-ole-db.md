---
description: ICommand (поставщик собственного клиента OLE DB)
title: ICommand (поставщик собственного клиента OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ICommand [SQL Server Native Client]
ms.assetid: 5e24b3a0-0658-44fc-b653-f4c52f9eb328
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: f261d8fa00650be277f145c43c13af0ab7c03fa9
ms.sourcegitcommit: 1a544cf4dd2720b124c3697d1e62ae7741db757c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2020
ms.locfileid: "97483195"
---
# <a name="icommand-native-client-ole-db-provider"></a>ICommand (поставщик собственного клиента OLE DB)
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  В этом разделе обсуждаются особенности OLE DB, касающиеся собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
## <a name="icommandexecute"></a>ICommand::Execute  
 Вставка данных, превышающих размер столбца, как правило, приводит к ошибке. Однако в некоторых ситуациях происходит возврат значения S_OK, хотя параметру *dwStatus* присваивается значение DBSTATUS_S_TRUNCATED. Обычно такая ситуация возникает при вставке данных с параметрами, когда размера столбца не хватает для размещения данных и не был вызван метод **ICommandWithParameters::SetParameterInfo** .  
  
## <a name="see-also"></a>См. также:  
 [Интерфейсы (OLE DB)](./sql-server-native-client-ole-db-interfaces.md)  
  
