---
description: Сведения о связанных с наборами записей ошибках
title: Recordset-Related сведения об ошибке | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- Recordset-related errors [ADO]
- errors [ADO], Recordset-related
ms.assetid: 7e103574-59ad-4790-b5f9-fa8d715e711e
author: rothja
ms.author: jroth
ms.openlocfilehash: 2fcd596455cc1074d46ea6ee45d6c1f037553741
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100037104"
---
# <a name="recordset-related-error-information"></a>Сведения о связанных с наборами записей ошибках
Во время пакетной обработки свойство **Status** объекта **Recordset** предоставляет сведения об отдельных записях в **наборе** записей. Перед обновлением пакетного обновления свойство **Status** **набора записей** отражает сведения о добавляемых, изменяемых и удаленных записях. После вызова **UpdateBatch** свойство **Status** указывает на успешное или неуспешное выполнение операции. При переходе от записи к записи в **наборе записей** значение свойства **Status** изменяется, чтобы описать состояние текущей записи.
