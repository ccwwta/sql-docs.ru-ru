---
description: Функция SQLRemoveDSNFromIni
title: Функция Склремоведснфромини | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLRemoveDSNFromIni
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLRemoveDSNFromIni
helpviewer_keywords:
- SQLRemoveDSNFromIni function [ODBC]
ms.assetid: bb2e8273-7b61-4113-bfc8-f7ccc607c811
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 26bbcf3bf68dda172220323cb7d9b0dc39e3178d
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99192488"
---
# <a name="sqlremovedsnfromini-function"></a>Функция SQLRemoveDSNFromIni
**Соответствия**  
 Введенная версия: ODBC 1,0  
  
 **Сводка**  
 **Склремоведснфромини** удаляет источник данных из сведений о системе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
  
BOOL SQLRemoveDSNFromIni(  
     LPCSTR   lpszDSN);  
```  
  
## <a name="arguments"></a>Аргументы  
 *лпсздсн*  
 Входной Имя удаляемого источника данных.  
  
## <a name="returns"></a>Возвращаемое значение  
 Функция возвращает значение TRUE, если удаляет источник данных, или источник данных отсутствовал в файле Odbc.ini. Он возвращает значение FALSE, если не удается удалить источник данных.  
  
## <a name="diagnostics"></a>Диагностика  
 Когда **склремоведснфромини** возвращает значение false, связанное значение *\* пферроркоде* может быть получено путем вызова **склинсталлереррор**. В следующей таблице перечислены значения *\* пферроркоде* , которые могут быть возвращены **склинсталлереррор** , и объясняется каждый из них в контексте этой функции.  
  
|*\*пферроркоде*|Ошибка|Описание|  
|---------------------|-----------|-----------------|  
|ODBC_ERROR_GENERAL_ERR|Общая ошибка установщика|Произошла ошибка, для которой не возникала конкретная ошибка установщика.|  
|ODBC_ERROR_INVALID_DSN|Недопустимое имя DSN|Недопустимый аргумент *лпсздсн* .|  
|ODBC_ERROR_REQUEST_FAILED|Не удалось выполнить запрос|Установщику не удалось удалить из реестра сведения о DSN.|  
|ODBC_ERROR_OUT_OF_MEM|Недостаточно памяти|Установщику не удалось выполнить функцию из-за нехватки памяти.|  
  
## <a name="comments"></a>Комментарии  
 **Склремоведснфромини** удаляет имя источника данных из раздела [источники данных ODBC] сведений о системе. Он также удаляет раздел спецификации источника данных из сведений о системе.  
  
 Эта функция должна вызываться только из библиотеки установки драйвера.  
  
## <a name="related-functions"></a>Связанные функции  
  
|Сведения о|См.|  
|---------------------------|---------|  
|Добавление, изменение или удаление источника данных|[ConfigDSN](../../../odbc/reference/syntax/configdsn-function.md)|  
|Добавление, изменение или удаление источника данных|[SQLConfigDataSource](../../../odbc/reference/syntax/sqlconfigdatasource-function.md)|  
|Удаление источника данных по умолчанию|[склремоведефаултдатасаурце](../../../odbc/reference/syntax/sqlremovedefaultdatasource-function.md)|  
|Добавление имени источника данных в сведения о системе|[склвритедснтоини](../../../odbc/reference/syntax/sqlwritedsntoini-function.md)|
