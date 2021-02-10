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
ms.openlocfilehash: 6994b3c5466622a32ad0d17e1a00424396d39ebc
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100021226"
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
  
## <a name="remarks"></a>Remarks  
 Этот метод не выполняет AddRef указателя на интерфейс. Если вызывающий объект планирует удерживать указатель, вызывающий объект должен выполнить требуемый метод AddRef и Release.  
  
## <a name="applies-to"></a>Применяется к  
 [Интерфейс IDSOShapeExtensions](./idsoshapeextensions-interface.md)