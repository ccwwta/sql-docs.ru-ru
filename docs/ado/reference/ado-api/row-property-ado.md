---
description: Свойство Row (ADO)
title: Свойство Row (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- ADORecordConstruction::PutRow
- ADORecordConstruction::GetRow
- ADORecordConstruction::get_Row
- ADORecordConstruction::Row
- ADORecordConstruction::put_Row
helpviewer_keywords:
- Row property [ADO]
ms.assetid: 21019d89-2dd1-4a26-ac6f-384b81d66949
author: rothja
ms.author: jroth
ms.openlocfilehash: e59240d9cb6419153e6f717521748ad6beca8e2a
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100040744"
---
# <a name="row-property-ado"></a>Свойство Row (ADO)
Возвращает или задает объект OLE DB **строки** из объекта [интерфейса адорекордконструктион](./adorecordconstruction-interface.md) или. При использовании **put_Row** для задания объекта **строки** строка преобразуется в объект **записи** ADO.  
  
## <a name="readwritesyntax"></a>Чтение и запись. Syntax  
  
```  
HRESULT get_Row([out, retval] IUnknown** ppRow);  
HRESULT put_Row([in] IUnknown* pRow);  
```  
  
## <a name="parameters"></a>Параметры  
 *ппров*  
 Указатель на объект **строки** OLE DB.  
  
 *пров*  
 Объект **строки** OLE DB.  
  
## <a name="return-values"></a>Возвращаемые значения  
 Этот метод свойства возвращает стандартные значения HRESULT, включая S_OK и E_FAIL.  
  
## <a name="applies-to"></a>Применение  
 [Интерфейс ADORecordConstruction](./adorecordconstruction-interface.md)