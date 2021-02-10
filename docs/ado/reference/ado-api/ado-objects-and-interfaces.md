---
description: Объекты и интерфейсы ADO
title: Объекты и интерфейсы ADO | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
helpviewer_keywords:
- ADO, objects and interfaces
- objects [ADO]
ms.assetid: d0b7e254-c89f-4406-b846-a060ef038c30
author: rothja
ms.author: jroth
ms.openlocfilehash: 64dc0e750a999fa1a333a3ec94576583850e511e
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100027950"
---
# <a name="ado-objects-and-interfaces"></a>Объекты и интерфейсы ADO
Связи между этими объектами представлены в [объектной модели ADO](./ado-object-model.md).  
  
 Каждый объект может содержаться в соответствующей коллекции. Например, объект [ошибки](./error-object.md) может содержаться в коллекции [Errors](./errors-collection-ado.md) . Дополнительные сведения см. в разделе [коллекции ADO](./ado-collections.md) или сведения о конкретной коллекции.  
  
|Объект или интерфейс|Описание|  
|-|-|  
|[иадокоммандконструктион](/previous-versions/windows/desktop/aa965677(v=vs.85))|Используется для получения базовой команды OLEDB из объекта Адокомманд.|  
|[адорекордконструктион](./adorecordconstruction-interface.md)|Конструирует объект **записи** ADO из объекта **строки** OLE DB в приложении C/C++.|  
|[адорекордсетконструктион](./adorecordsetconstruction-interface.md)|Конструирует объект **набора записей** ADO из объекта OLE DB **набора строк** в приложении C/C++.|  
|[Интерфейс ADOStreamConstruction](./adostreamconstruction-interface.md)|Конструирует объект **потока** ADO из OLE DBного объекта **IStream** в приложении C/C++.|  
|[Command](./command-object-ado.md)|Определяет конкретную команду, которую необходимо выполнить для источника данных.<br /><br /> Объект **Command** не является надежным для сценариев.|  
|[Соединение](./connection-object-ado.md)|Представляет открытое подключение к источнику данных.<br /><br /> Объект **соединения** является надежным для сценариев.|  
|[Интерфейс IDSOShapeExtensions](./idsoshapeextensions-interface.md)|Возвращает базовый объект источника данных OLEDB для поставщика фигур.|  
|[Ошибка](./error-object.md)|Содержит сведения об ошибках доступа к данным, относящихся к одной операции, включающей в себя поставщик.<br /><br /> Объект **Error** не является надежным для скриптов.|  
|[Поле](./field-object.md)|Представляет столбец данных с общим типом данных.|  
|[Параметр](./parameter-object.md)|Представляет параметр или аргумент, связанный с объектом **Command** на основе параметризованного запроса или хранимой процедуры.<br /><br /> Объект **параметра** не является надежным для скриптов.|  
|[Свойство](./property-object-ado.md)|Представляет динамическую характеристику объекта ADO, определяемого поставщиком.|  
|[Запись](./record-object-ado.md)|Представляет строку **набора записей** или каталога или файла в файловой системе. Объект **Record** является надежным для сценариев.|  
|[набор записей](./recordset-object-ado.md)|Представляет набор записей из базовой таблицы или результаты выполненной команды. В любой момент времени объект **Recordset** ссылается только на одну запись в наборе в качестве текущей записи.<br /><br /> Объект **набора записей** является надежным для сценариев.|  
|[STREAM](./stream-object-ado.md)|Представляет двоичный поток данных.<br /><br /> Объект **потока** является надежным для скриптов.|  
  
## <a name="see-also"></a>См. также:  
 [Справочник по API ADO](./ado-api-reference.md)   
 [Коллекции ADO](./ado-collections.md)   
 [Динамические свойства ADO](./ado-dynamic-properties.md)   
 [Перечислимые константы ADO](./ado-enumerated-constants.md)   
 [Приложение б. ошибки ADO](../../guide/appendixes/appendix-b-ado-errors.md)   
 [События ADO](./ado-events.md)   
 [Методы ADO](./ado-methods.md)   
 [Объектная модель ADO](./ado-object-model.md)   
 [Свойства ADO](./ado-properties.md)