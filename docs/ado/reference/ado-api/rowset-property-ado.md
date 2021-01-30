---
description: Свойство Rowset (ADO)
title: Свойство Rowset (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- ADORecordsetConstruction::PutRowset
- ADORecordsetConstruction::GetRowset
- ADORecordsetConstruction::Rowset
- ADORecordsetConstruction::put_Rowset
- ADORecordsetConstruction::get_Rowset
helpviewer_keywords:
- Rowset property [ADO]
ms.assetid: 7d359294-4ff2-47e0-8111-0c221b24d80e
author: rothja
ms.author: jroth
ms.openlocfilehash: 1f5e99f97179323e92ff04153b5cb9fe0d67fe46
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99170339"
---
# <a name="rowset-property-ado"></a>Свойство Rowset (ADO)
Возвращает или задает OLE DB объект **набора строк** из объекта **адорекордсетконструктион** или. При использовании put_Rowset набор строк превращается в объект **набора записей** ADO.  
  
 Read/write.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT get_Rowset([out, retval] IUnknown** ppRowset);  
HRESULT put_Rowset([in] IUnknown* pRowset);  
```  
  
## <a name="parameters"></a>Параметры  
 *ppRowset*  
 Указатель на объект **набора строк** OLE DB.  
  
 *провсет*  
 Объект OLE DB **набора строк** .  
  
## <a name="return-values"></a>Возвращаемые значения  
 Этот метод свойства возвращает стандартные значения HRESULT, включая S_OK и E_FAIL.  
  
## <a name="applies-to"></a>Применение  
 [Интерфейс ADORecordsetConstruction](./adorecordsetconstruction-interface.md)