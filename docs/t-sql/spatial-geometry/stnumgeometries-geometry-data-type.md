---
description: STNumGeometries (тип данных geometry)
title: STNumGeometries (тип данных geometry) | Документы Майкрософт
ms.custom: ''
ms.date: 08/03/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: reference
f1_keywords:
- STNumGeometries (geometry Data Type)
- STNumGeometries_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- STNumGeometries (geometry Data Type)
ms.assetid: 9402b03d-3039-42ca-ac59-f96b7f1a48de
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: f988829d747889feeca37a538c4a0cb565d9dea6
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99181772"
---
# <a name="stnumgeometries-geometry-data-type"></a>STNumGeometries (тип данных geometry)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

Возвращает количество геометрических объектов, составляющих экземпляр **geometry**.
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
.STNumGeometries ( )  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="return-types"></a>Типы возвращаемых данных
 Тип возвращаемых данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **int**  
  
 Тип возвращаемых данных CLR: **SqlInt32**  
  
## <a name="remarks"></a>Примечания  
 Этот метод возвращает значение 1, если экземпляр **geometry** не является экземпляром **MultiPoint**, **MultiLineString**, **MultiPolygon** или **GeometryCollection**, либо значение 0, если экземпляр **geometry** пуст.  
  
> [!NOTE]  
>  Если в коллекции **GeometryCollection** есть пустые вложенные элементы, то функция `STNumGeometries()` не возвратит значение 0. Несмотря на то, что элементы из экземпляра **GeometryCollection** пусты, сам экземпляр не является пустым набором.  
  
  

