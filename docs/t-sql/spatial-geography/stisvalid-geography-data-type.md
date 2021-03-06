---
description: STIsValid (тип данных geography)
title: STIsValid (тип данных geography) | Документы Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- STIsValid method (geography)
ms.assetid: 1bfe787f-ddf0-4fc7-af6a-570a58faab23
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 546b69e32302a44f2e7121a55636fd042c7972b1
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99158877"
---
# <a name="stisvalid-geography-data-type"></a>STIsValid (тип данных geography)
[!INCLUDE [SQL Server Azure SQL Database ](../../includes/applies-to-version/sql-asdb.md)]

  Возвращает значение true, если экземпляр **geography** корректен и распознается как допустимый географический объект на основе типа открытого геопространственного консорциума (OGC). Возвращает значение false, если экземпляр **geography** имеет неправильный формат. Этот метод является точным.  
  
 Этот метод типа данных geography поддерживает экземпляры **FullGlobe** или пространственные экземпляры, размер которых больше полушария.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
.STIsValid ( )  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="return-types"></a>Типы возвращаемых данных
 Тип возвращаемых данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **bit**  
  
 Тип возвращаемых данных CLR: **SqlBoolean**  
  
## <a name="remarks"></a>Комментарии  
 Тип OGC экземпляра **geography** можно определить с помощью метода [STGeometryType()](../../t-sql/spatial-geography/stgeometrytype-geography-data-type.md).  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] формирует только допустимые экземпляры **geography**, однако позволяет хранить и получать недопустимые экземпляры. Допустимый экземпляр, представляющий тот же набор точек, что и недопустимый экземпляр, может быть получен с помощью метода `MakeValid()`.  
  
## <a name="examples"></a>Примеры  
 В следующем примере создается экземпляр `geography` и используется метод `STIsValid()`, чтобы проверить, допустим ли экземпляр.  
  
```  
DECLARE @g geography = geography::STGeomFromText('LINESTRING(0 0, 2 2, 1 0)', 4326);  
SELECT @g.STIsValid();  
DECLARE @g geography  
```  
  
## <a name="see-also"></a>См. также:  
 [STGeometryType (тип данных geography)](../../t-sql/spatial-geography/stgeometrytype-geography-data-type.md)   
 [MakeValid (тип данных geography)](../../t-sql/spatial-geography/makevalid-geography-data-type.md)   
 [Методы OGC в экземплярах Geography](../../t-sql/spatial-geography/ogc-methods-on-geography-instances.md)  
  
  
