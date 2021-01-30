---
description: Метод get_OLEDBCommand
title: Метод get_OLEDBCommand | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
helpviewer_keywords:
- get_OLEDBCommand method [ADO]
ms.assetid: 23d551f5-3d5b-434b-ade6-fef15f1710e7
author: rothja
ms.author: jroth
ms.openlocfilehash: edd8816389088c077f43ed7b36f01ebd61010e98
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99171012"
---
# <a name="get_oledbcommand-method"></a>Метод get_OLEDBCommand
Возвращает базовую команду OLE DB, которая сначала распространяет все сведения о параметрах, заданные в команде ADO, в команду OLE DB.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
HRESULT get_OLEDBCommand(  
      IUnknown **ppOLEDBCommand  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *пполедбкомманд*  
 заполняет Указатель на расположение указателя, в котором будет записан указатель IUnknown для базовой OLE DBной команды.  
  
## <a name="applies-to"></a>Применение  
 [иадокоммандконструктион](/previous-versions/windows/desktop/aa965677(v=vs.85))