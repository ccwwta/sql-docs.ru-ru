---
description: Свойство ParentRow (ADO)
title: Свойство ParentRow (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- ADORecordConstruction::put_ParentRow
- ADORecordConstruction::ParentRow
- ADORecordConstruction::putParentRow
helpviewer_keywords:
- ParentRow property [ADO]
ms.assetid: 5ea8029b-eda4-490b-ae84-2ad036fb582f
author: rothja
ms.author: jroth
ms.openlocfilehash: 115689c06ce4bdb387b126ecc6087e63c705dcdc
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99170589"
---
# <a name="parentrow-property-ado"></a>Свойство ParentRow (ADO)
Задает контейнер объекта OLE DB **строки** для объекта **адорекордконструктион** , чтобы родительский элемент строки был включен в объект **записи** ADO.  
  
 Доступный только на запись.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT put_ParentRow([in] IUnknown* pParent);  
```  
  
## <a name="parameters"></a>Параметры  
 *ппарент*  
 Контейнер строки.  
  
## <a name="return-values"></a>Возвращаемые значения  
 Этот метод свойства возвращает стандартные значения HRESULT, включая S_OK и E_FAIL.  
  
## <a name="applies-to"></a>Применение  
 [Интерфейс ADORecordConstruction](./adorecordconstruction-interface.md)