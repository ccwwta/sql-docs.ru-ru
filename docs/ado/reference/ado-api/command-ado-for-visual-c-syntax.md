---
description: Command (синтаксис ADO для Visual C++)
title: Command (ADO для синтаксиса Visual C++) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
dev_langs:
- C++
helpviewer_keywords:
- Command collection [ADO], ADO for Visual C++ syntax
ms.assetid: cf12cbd1-25f7-4bb5-aa94-0fe823b3b6d6
author: rothja
ms.author: jroth
ms.openlocfilehash: b6b9dc331d75370b515253f57a8c249fc54dac49
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99171493"
---
# <a name="command-ado-for-visual-c-syntax"></a>Command (синтаксис ADO для Visual C++)
## <a name="methods"></a>Методы  
  
```  
Cancel(void)  
CreateParameter(BSTR Name, DataTypeEnum Type, ParameterDirectionEnum Direction, long Size, VARIANT Value, _ADOParameter **ppiprm)  
Execute(VARIANT *RecordsAffected, VARIANT *Parameters, long Options, _ADORecordset **ppirs)  
```  
  
## <a name="properties"></a>Свойства  
  
```  
get_ActiveConnection(_ADOConnection **ppvObject)  
put_ActiveConnection(VARIANT vConn)  
putref_ActiveConnection(_ADOConnection *pCon)  
get_CommandText(BSTR *pbstr)  
put_CommandText(BSTR bstr)  
get_CommandTimeout(LONG *pl)  
put_CommandTimeout(LONG Timeout)  
get_CommandType(CommandTypeEnum *plCmdType)  
put_CommandType(CommandTypeEnum lCmdType)  
get_Name(BSTR *pbstrName)  
put_Name(BSTR bstrName)  
get_Prepared(VARIANT_BOOL *pfPrepared)  
put_Prepared(VARIANT_BOOL fPrepared)  
get_State(LONG *plObjState)  
get_Parameters(ADOParameters **ppvObject)  
```  
  
## <a name="see-also"></a>См. также:  
 [Объект Command (ADO)](./command-object-ado.md)