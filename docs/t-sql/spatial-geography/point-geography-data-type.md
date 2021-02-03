---
description: Point (тип данных geography)
title: Point (тип данных geography) | Документы Майкрософт
ms.custom: ''
ms.date: 10/10/2019
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: reference
f1_keywords:
- Point
- Point_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- Point method
- Point (geography Data Type)
ms.assetid: 0dc6f422-7aae-4016-b7f4-3289fa8f989c
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 207b4c8fb9c9d171e7caad003e9b398c97dc4152
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99210146"
---
# <a name="point-geography-data-type"></a>Point (тип данных geography)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

Создает экземпляр **geography**, представляющий экземпляр **Point**, по значениям широты и долготы и идентификатору пространственной ссылки (SRID).
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Point ( Lat, Long, SRID )  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>Аргументы
 *Lat*  
 Выражение типа **float**, представляющее координату по оси Y создаваемого экземпляра **Point**.  
  
 *Long*  
 Выражение **float**, представляющее координату по оси X создаваемого экземпляра **Point**. Дополнительные сведения о допустимых значениях широты и долготы см. в разделе [Point](../../relational-databases/spatial/point.md).  
  
 *SRID*  
 Выражение типа **int**, представляющее [идентификатор пространственной ссылки](../../relational-databases/spatial/spatial-reference-identifiers-srids.md) возвращаемого экземпляра **geography**.  
  
> [!NOTE]  
>  Аргументы для метода точки (тип данных geography) имеют обратные координаты по сравнению с WKT.  
  
## <a name="return-types"></a>Типы возвращаемых данных  
 Тип возвращаемых данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **geography**  
  
 Тип возвращаемого значения CLR: **SqlGeography**  
  
## <a name="examples"></a>Примеры  
 В следующем примере метод `Point()` применяется для создания экземпляра `geography`.  
  
```  
DECLARE @g geography;   
SET @g = geography::Point(47.65100, -122.34900, 4326)  
SELECT @g.ToString();  
```  
  
## <a name="see-also"></a>См. также:  
 [Расширенные статические географические методы](../../t-sql/spatial-geography/extended-static-geography-methods.md)