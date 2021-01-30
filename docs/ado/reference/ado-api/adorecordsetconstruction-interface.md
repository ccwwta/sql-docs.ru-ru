---
description: Интерфейс ADORecordsetConstruction
title: Интерфейс Адорекордсетконструктион | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- ADORecordsetConstruction
helpviewer_keywords:
- ADORecordsetConstruction interface [ADO]
ms.assetid: 08386eba-f1f7-4879-8ffd-8733930ecb2f
author: rothja
ms.author: jroth
ms.openlocfilehash: d9be4f47033616f56177027bc83c4621cef57847
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99164868"
---
# <a name="adorecordsetconstruction-interface"></a>Интерфейс ADORecordsetConstruction
Интерфейс **адорекордсетконструктион** используется для создания объекта **набора записей** ADO из объекта OLE DB **набора строк** в приложении C/C++.  
  
 Этот интерфейс поддерживает следующие свойства:  
  
## <a name="properties"></a>Свойства  
  
|Свойство|Описание|  
|-|-|  
|[Глава](./chapter-property-ado.md)|Чтение и запись.<br />Получает или задает OLE DB объект **главы** от/в этом объекте ADO **Recordset** .|  
|[ровпоситион](./rowposition-property-ado.md)|Чтение и запись.<br />Возвращает или задает OLE DB объект **ровпоситион** из или в этом объекте ADO **Recordset** .|  
|[Набор строк](./rowset-property-ado.md)|Чтение и запись.<br />Возвращает или задает OLE DB объект **набора строк** из или в этом объекте ADO **Recordset** .|  
  
## <a name="methods"></a>Методы  
 Нет.  
  
## <a name="events"></a>События  
 Нет.  
  
## <a name="remarks"></a>Remarks  
 При наличии объекта **набора строк** OLE DB ( `pRowset` ) построение объекта **набора записей** ADO () производится `adoRs` в следующие три основные операции:  
  
1.  Создайте объект **набора записей** ADO.  
  
    ```  
    Recordset20Ptr adoRs;  
    adoRs.CreateInstance(__uuidof(Recordset));  
    ```  
  
2.  Запросите интерфейс **иадорекордсетконструктион** в объекте **Recordset** :  
  
    ```  
    adoRecordsetConstructionPtr adoRsConstruct=NULL;  
    adoRs->QueryInterface(__uuidof(ADORecordsetConstruction),  
                         (void**)&adoRsConstruct);  
    ```  
  
3.  Вызовите `IADORecordsetConstruction::put_Rowset` метод Property, чтобы задать `Rowset` объект OLE DB `Recordset` объекта ADO:  
  
    ```  
    IUnknown *pUnk=NULL;  
    pRowset->QueryInterface(IID_IUnknown, (void**)&pUnk);  
    adoRsConstruct->put_Rowset(pUnk);  
    ```  
  
 Результирующий `adoRs` объект теперь представляет объект ADO **Recordset** , созданный из объекта OLE DB **Rowset** .  
  
 Можно также создать объект **набора записей** ADO из OLE DB **главы** или объекта **ровпоситион** .  
  
## <a name="requirements"></a>Требования  
 **Версия:** ADO 2,0 и более поздние версии  
  
 **Библиотека:** msado15.dll  
  
 **UUID:** 00000283-0000-0010-8000-00AA006D2EA4  
  
## <a name="see-also"></a>См. также:  
 [Объект Recordset (ADO)](./recordset-object-ado.md)   
 [Свойство Rowset (ADO)](./rowset-property-ado.md)