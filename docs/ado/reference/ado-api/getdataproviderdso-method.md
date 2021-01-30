---
description: Метод GetDataProviderDSO
title: Метод Жетдатапровидердсо | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
helpviewer_keywords:
- GetDataProviderDSO Method [ADO]
ms.assetid: 5a4c6bd5-0c79-4f81-a977-0561392d8d50
author: rothja
ms.author: jroth
ms.openlocfilehash: c784e5c3951f78ef28bfd0d0008570d1b1e68ca8
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99167281"
---
# <a name="getdataproviderdso-method"></a>Метод GetDataProviderDSO
Извлекает базовый объект источника данных OLE DB из поставщика фигур.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
HRESULT GetDataProviderDSO(  
      IUnknown **ppDataProviderDSOIUnknown  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *ппдатапровидердсоиункновн*  
 заполняет  Указатель на указатель, возвращающий IUnknown базового OLE DB объекта источника данных.  
  
## <a name="remarks"></a>Замечания  
 Этот метод не выполняет AddRef указателя на интерфейс. Если вызывающий объект планирует удерживать указатель, вызывающий объект должен выполнить требуемый метод AddRef и Release.  
  
## <a name="applies-to"></a>Применяется к  
 [Интерфейс IDSOShapeExtensions](./idsoshapeextensions-interface.md)