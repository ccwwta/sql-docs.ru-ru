---
description: Сохранение иерархических наборов записей
title: Сохранение иерархических наборов записей | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- hierarchical Recordsets [ADO], persisting
- persisting hierarchical Recordsets [ADO]
- data shaping [ADO], hierarchical Recordsets
ms.assetid: 43798bb5-98a6-4ad6-9bf8-78154b3a1827
author: rothja
ms.author: jroth
ms.openlocfilehash: ddcda766d729e085ed654757d0125f18ec7a696a
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100037194"
---
# <a name="persisting-hierarchical-recordsets"></a>Сохранение иерархических наборов записей
Можно сохранить иерархический **набор записей** в файл в формате АДТГ или XML, вызвав метод [Save](../../../ado/reference/ado-api/save-method.md) . Однако при сохранении иерархических **наборов записей** в формате XML применяются два ограничения: невозможно сохранить в XML, если иерархический **набор** записей содержит ожидающие обновления, и нельзя сохранить параметризованный иерархический **набор записей**.  
  
 Дополнительные сведения о поставщике формирования данных см. в статьях [Служба формирования данных Майкрософт для OLE DB](../../../ado/guide/appendixes/microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) (ADO) и [Общие сведения о службе формирования данных для OLE DB](/previous-versions/windows/desktop/ms719615(v=vs.85)).  
  
## <a name="see-also"></a>См. также:  
 [Пример формирования данных](../../../ado/guide/data/data-shaping-example.md)   
 [Грамматика формальной фигуры](../../../ado/guide/data/formal-shape-grammar.md)   
 [Общие сведения о командах формирования данных](../../../ado/guide/data/shape-commands-in-general.md)