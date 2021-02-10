---
description: Свойство Source (объект Recordset ADO)
title: Свойство Source (набор записей ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Recordset15::putref_Source
- Recordset15::Source
- Recordset15::PutSource
- Recordset15::get_Source
- Recordset15::GetSource
- Recordset15::PutRefSource
- Recordset15::put_Source
helpviewer_keywords:
- Source property [ADO Recordset]
ms.assetid: a05ba2c9-2821-4343-8607-4de9b764ec91
author: rothja
ms.author: jroth
ms.openlocfilehash: 04287b1fca3b3716302ab440f8f5213cff3f6302
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100051375"
---
# <a name="source-property-ado-recordset"></a>Свойство Source (объект Recordset ADO)
Указывает источник данных для объекта [набора записей](./recordset-object-ado.md) .  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает **строковое** значение или ссылку на объект [команды](./command-object-ado.md) ; Возвращает только **строковое** значение, указывающее источник **набора записей**.  
  
## <a name="remarks"></a>Remarks  
 Используйте свойство **Source** , чтобы указать источник данных для объекта **набора записей** , используя одну из следующих команд: переменная объекта **команды** , инструкция SQL, хранимая процедура или имя таблицы.  
  
 Если задать для свойства **Source** объект **Command** , свойство [ActiveConnection](./activeconnection-property-ado.md) объекта **Recordset** будет наследовать значение свойства **ActiveConnection** для указанного объекта **команды** . Однако чтение свойства **Source** не приводит к возврату объекта **Command** . Вместо этого возвращается свойство [CommandText](./commandtext-property-ado.md) объекта **Command** , для которого задается **исходное** свойство.  
  
 Если свойство **Source** является инструкцией SQL, хранимой процедурой или именем таблицы, можно оптимизировать производительность, передав соответствующий аргумент *Options* вызову метода [Open](./open-method-ado-recordset.md) .  
  
 Свойство **Source** доступно для чтения и записи закрытых объектов **Recordset** и доступно только для чтения для открытых объектов **Recordset** .  
  
## <a name="applies-to"></a>Применение  
 [Объект Recordset (ADO)](./recordset-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример свойства Source (Visual Basic)](./source-property-example-vb.md)   
 [Свойство Source (ошибка ADO)](./source-property-ado-error.md)   
 [Свойство Source (объект Record ADO)](./source-property-ado-record.md)