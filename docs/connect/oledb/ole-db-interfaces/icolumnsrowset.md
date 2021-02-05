---
title: IColumnsRowset (драйвер OLE DB) | Документация Майкрософт
description: Столбец DBCOLUMN_BASETABLEINSTANCE в IColumnsRowset::GetColumnRowset зарезервирован для использования корпорацией Майкрософт в OLE DB Driver for SQL Server.
ms.custom: ''
ms.date: 06/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 040052f04cdee697a616aa7ced6d790601d0c829
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99191814"
---
# <a name="icolumnsrowset"></a>IColumnsRowset
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  OLE DB Driver for SQL Server добавляет столбец DBCOLUMN_BASETABLEINSTANCE в набор, возвращаемый методом IColumnsRowset::GetColumnRowset. Этот столбец имеет тип данных DBTYPE_I2 и зарезервирован корпорацией Майкрософт для будущего использования. В будущих версиях данные из этого столбца могут быть изменены.  
  
## <a name="see-also"></a>См. также:  
 [Интерфейсы (OLE DB)](../../oledb/ole-db-interfaces/oledb-driver-for-sql-server-ole-db-interfaces.md) 
  
  
