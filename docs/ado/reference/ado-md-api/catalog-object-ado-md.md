---
description: Объект Catalog (многомерные объекты ADO)
title: Объект каталога (объекты данных ActiveX (MD)) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Catalog
helpviewer_keywords:
- Catalog object [ADO MD]
ms.assetid: 11f6f896-d69c-44a4-94cd-d54c93140e4a
author: rothja
ms.author: jroth
ms.openlocfilehash: 834594c957c05d4e2acef78bb772afcbe83b685a
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99169972"
---
# <a name="catalog-object-ado-md"></a>Объект Catalog (многомерные объекты ADO)
Содержит сведения о многомерной схеме (то есть Кубы и базовые измерения, иерархии, уровни и элементы), относящиеся к поставщику многомерных данных (MDP).  
  
## <a name="remarks"></a>Замечания  
 С помощью коллекций и свойств объекта **каталога** можно выполнять следующие действия.  
  
-   Откройте каталог, задав для свойства [ActiveConnection](./activeconnection-property-ado-md.md) стандартный объект [соединения](../ado-api/connection-object-ado.md) ADO или допустимую строку подключения.  
  
-   Найдите **Каталог** со свойством [Name](./name-property-ado-md.md) .  
  
-   Выполните итерацию по кубам в каталоге, используя коллекцию [кубедефс](./cubedefs-collection-ado-md.md) .  
  
 Этот раздел содержит следующий раздел.  
  
-   [Свойства, методы и события](./catalog-object-properties-methods-and-events-ado-md.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример каталога (VB)](./catalog-example-vb.md)   
 [Объект Connection (ADO)](../ado-api/connection-object-ado.md)   
 [Коллекция CubeDefs (многомерные объекты ADO)](./cubedefs-collection-ado-md.md)