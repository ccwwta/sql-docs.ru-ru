---
description: STNumPoints (тип данных geometry)
title: STNumPoints (тип данных geometry) | Документы Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: reference
f1_keywords:
- STNumPoints_TSQL
- STNumPoints (geometry Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- STNumPoints (geometry Data Type)
ms.assetid: a19520fc-7f91-4a2c-856f-4d8b99a7e496
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: aef97340f845f15cc8a86e0d4758b5fa7dc33229
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99181718"
---
# <a name="stnumpoints-geometry-data-type"></a>STNumPoints (тип данных geometry)
[!INCLUDE [SQL Server Azure SQL Database ](../../includes/applies-to-version/sql-asdb.md)]

  Возвращает суммарное количество точек в каждой из фигур в экземпляре **geometry**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
.STNumPoints ( )  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="return-types"></a>Типы возвращаемых данных
 Тип возвращаемых данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **int**  
  
 Тип возвращаемых данных CLR: **SqlInt32**  
  
## <a name="remarks"></a>Примечания  
 Этот метод подсчитывает число точек в описании экземпляра **geometry**. Повторяющиеся точки учитываются. Если этот экземпляр принадлежит к типу **collection**, то метод возвращает сумму точек в каждом из его элементов.  
  
## <a name="examples"></a>Примеры  
 В следующем примере создается экземпляр `LineString` и вызывается метод `STNumPoints()`, определяющий число точек, использованных в его описании.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('LINESTRING(0 0, 2 2, 1 0)', 0);  
SELECT @g.STNumPoints();  
```  
  
## <a name="see-also"></a>См. также:  
 [Методы OGC в экземплярах Geometry](../../t-sql/spatial-geometry/ogc-methods-on-geometry-instances.md)  
  
  
