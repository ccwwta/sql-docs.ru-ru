---
description: Изменение существующих записей
title: Изменение существующих записей | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- editing data [ADO], existing records
ms.assetid: 17ce1263-5897-452a-9ea5-c7f96b33df65
author: rothja
ms.author: jroth
ms.openlocfilehash: 031d819e2c8eed63b9b8ff42aa58fb8e998a4273
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100037504"
---
# <a name="editing-existing-records"></a>Изменение существующих записей
Чтобы изменить существующие записи, перейдите к строке, которую необходимо изменить, и измените свойство **значения** полей, которые необходимо изменить. Дополнительные сведения о свойстве **value** объекта **field** см. в разделе [анализ данных](./examining-data.md). В зависимости от типа курсора для отправки изменений обратно в источник данных будет использоваться **Update** или **UpdateBatch** . Дополнительные сведения см. в разделе [обновление и сохранение данных](./updating-and-persisting-data.md).  
  
 Обычно более эффективно использовать хранимую процедуру с объектом Command для выполнения обновлений, а также выполнять другие операции, так как хранимая процедура не требует создания курсора. Дополнительные сведения о курсорах см. в разделе Основные сведения о курсорах [и блокировках](./understanding-cursors-and-locks.md).