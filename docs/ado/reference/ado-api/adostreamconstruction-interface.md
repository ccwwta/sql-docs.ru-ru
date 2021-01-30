---
description: Интерфейс ADOStreamConstruction
title: Интерфейс Адостреамконструктион | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- ADOStreamConstruction
helpviewer_keywords:
- ADOStreamConstruction interface [ADO]
ms.assetid: 92f5a939-3e1a-4b14-a9dd-90e6ce2dec74
author: rothja
ms.author: jroth
ms.openlocfilehash: 1138d00d291ffdabf415177a948bf87b1c6502a8
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99171584"
---
# <a name="adostreamconstruction-interface"></a>Интерфейс ADOStreamConstruction
Интерфейс **адостреамконструктион** используется для создания объекта **потока** ADO из OLE DB объекта **IStream** в приложении C/C++.  
  
## <a name="properties"></a>Свойства  
  
|Свойство|Описание|  
|-|-|  
|[Поток](./stream-property.md)|Чтение и запись. Возвращает или задает объект OLE DB **потока** .|  
  
## <a name="methods"></a>Методы  
 Нет.  
  
## <a name="events"></a>События  
 Нет.  
  
## <a name="remarks"></a>Remarks  
 При наличии объекта OLE DB **IStream** ( `pStream` ) построение объекта **потока** ADO ( `adoStr` ) производится в следующие три основные операции:  
  
1.  Создайте объект **потока** ADO:  
  
    ```  
    Stream20Ptr adoStr;  
    adoStr.CreateInstance(__uuidof(Stream));  
    ```  
  
2.  Запросите интерфейс **иадостреамконструктион** в объекте **потока** :  
  
    ```  
    adoStreamConstructionPtr adoStrConstruct=NULL;  
    adoStr->QueryInterface(__uuidof(ADOStreamConstruction),  
                         (void**)&adoStrConstruct);  
    ```  
  
 Вызовите `IADOStreamConstruction::get_Stream` метод Property, чтобы задать OLE DB объект **IStream** в объекте **потока** ADO:  
  
```  
IUnknown *pUnk=NULL;  
pRowset->QueryInterface(IID_IUnknown, (void**)&pUnk);  
adoStrConstruct->put_Stream(pUnk);  
```  
  
 Результирующий `adoStr` объект теперь представляет объект **потока** ADO, созданный из OLE DB объекта **IStream** .  
  
## <a name="requirements"></a>Требования  
 **Версия:** ADO 2,0 или более поздняя версия  
  
 **Библиотека:** msado15.dll  
  
 **UUID:** 00000283-0000-0010-8000-00AA006D2EA4  
  
## <a name="see-also"></a>См. также:  
 [Справочник по API ADO](./ado-api-reference.md)