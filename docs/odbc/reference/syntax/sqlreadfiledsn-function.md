---
description: Функция SQLReadFileDSN
title: Функция Склреадфиледсн | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- SQLReadFileDSN
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLReadFileDSN
helpviewer_keywords:
- SQLReadFileDSN function [ODBC]
ms.assetid: ead464aa-cdc3-47dd-a0c0-997711205d31
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 7a04747258f612a86746642ae11fb06e9b742662
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99192539"
---
# <a name="sqlreadfiledsn-function"></a>Функция SQLReadFileDSN
**Соответствия**  
 Введенная версия: ODBC 3,0  
  
 **Сводка**  
 **Склреадфиледсн** считывает сведения из файлового DSN.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
  
BOOL SQLReadFileDSN(  
     LPCSTR   lpszFileName,  
     LPCSTR   lpszAppName,  
     LPCSTR   lpszKeyName,  
     LPSTR    lpszString,  
     WORD     cbString,  
     WORD *   pcbString);  
```  
  
## <a name="arguments"></a>Аргументы  
 *лпсзфиленаме*  
 Входной Указатель на буфер данных, содержащий имя файла DSN. Расширение имени DSN добавляется ко всем именам файлов, у которых еще нет расширения. DSN. Значение в *\* лпсзфиленаме* должно быть строкой, завершающейся нулем.  
  
 *лпсзаппнаме*  
 Входной Указатель на буфер данных, содержащий имя приложения. Это "ODBC" для раздела ODBC. Значение в *\* лпсзаппнаме* должно быть строкой, завершающейся нулем.  
  
 *лпсзкэйнаме*  
 Входной Указатель на буфер данных, содержащий имя ключа для чтения. Зарезервированные ключевые слова см. в разделе "Комментарии". Значение в *\* лпсзаппнаме* должно быть строкой, завершающейся нулем.  
  
 *лпсзстринг*  
 Проверки Указатель на буфер данных, содержащий строку, связанную с ключом, который необходимо считать.  
  
 Если *\* лпсзфиленаме* является допустимым именем DSN-файла, но аргумент *лпсзаппнаме* является пустым указателем, а аргумент *лпсзкэйнаме* — пустым указателем, *\* лпсзстринг* содержит список допустимых приложений. Если *\* лпсзфиленаме* является допустимым именем файла DSN, а *\* лпсзаппнаме* является допустимым именем приложения, но аргумент *лпсзкэйнаме* является пустым указателем, *\* лпсзстринг* содержит список допустимых зарезервированных ключевых слов в соответствующем разделе файла DSN, разделенных точкой с запятой. Если *\* лпсзфиленаме* является допустимым именем DSN-файла, но *\* лпсзаппнаме* является пустым указателем, а аргумент *лпсзкэйнаме* — пустым указателем, *\* лпсзстринг* содержит список разделов в файле DSN, разделенных точкой с запятой.  
  
 *кбстринг*  
 Входной Длина буфера *\* лпсзстринг* .  
  
 *пкбстринг*  
 Проверки Общее число байт, доступных для возврата в *\* лпсзстринг*. Если число возвращаемых байт больше или равно *кбстринг*, то выходная строка в *\* Лпсзстринг* усекается до *кбстринг* минус символ завершения null. Аргумент *пкбстринг* может быть пустым указателем.  
  
## <a name="returns"></a>Возвращаемое значение  
 Функция возвращает TRUE, если она успешна, и FALSE в случае сбоя.  
  
## <a name="diagnostics"></a>Диагностика  
 Когда **склреадфиледсн** возвращает значение false, связанное значение *\* пферроркоде* может быть получено путем вызова **склинсталлереррор**. В следующей таблице перечислены значения *\* пферроркоде* , которые могут быть возвращены **склинсталлереррор** , и объясняется каждый из них в контексте этой функции.  
  
|*\*пферроркоде*|Ошибка|Описание|  
|---------------------|-----------|-----------------|  
|ODBC_ERROR_GENERAL_ERR|Общая ошибка установщика|Произошла ошибка, для которой не возникала конкретная ошибка установщика.|  
|ODBC_ERROR_INVALID_BUFF_LEN|Недопустимая длина буфера|Аргумент *лпсзстринг* имеет значение null.<br /><br /> Аргумент *кбстринг* меньше или равен 0.|  
|ODBC_ERROR_INVALID_PATH|Недопустимый путь установки|Недопустимый путь к имени файла, указанному в аргументе *лпсзфиленаме* .|  
|ODBC_ERROR_INVALID_REQUEST_TYPE|Недопустимый тип запроса|Аргумент *лпсзаппнаме* имел значение null, в то время как аргумент *лпсзкэйнаме* является допустимым.|  
|ODBC_ERROR_OUT_OF_MEM|Недостаточно памяти|Установщику не удалось выполнить функцию из-за нехватки памяти.|  
|ODBC_ERROR_OUTPUT_STRING_TRUNCATED|Строка выходных данных усечена|Строка, возвращенная в *\* лпсзстринг* , была усечена, так как значение в *кбстринг* было меньше или равно значению в *\* пкбстринг*.|  
|ODBC_ERROR_REQUEST_FAILED|Не удалось выполнить запрос|Ключевое слово не существует в файле DSN.|  
  
## <a name="comments"></a>Комментарии  
 ODBC резервирует имя раздела [ODBC], в котором хранятся сведения о соединении. Зарезервированные ключевые слова для этого раздела совпадают с зарезервированными для строки подключения в **SQLDriverConnect**. (Дополнительные сведения см. в описании функции [SQLDriverConnect](../../../odbc/reference/syntax/sqldriverconnect-function.md) .)  
  
 Приложения могут использовать эти зарезервированные ключевые слова для чтения информации в файловом DSN. Если приложения хотят найти строку подключения без имени DSN, связанную с файлом DSN, он может вызвать **склреадфиледсн** для всех зарезервированных ключевых слов строки подключения в разделе [ODBC]. Полная строка подключения, переданная в соединении без имени DSN, является сочетанием всех ключевых слов (зарезервированных и зависящих от драйвера) в разделе [ODBC].  
  
## <a name="related-functions"></a>Связанные функции  
  
|Сведения о|См.|  
|---------------------------|---------|  
|Запись сведений в Файловый DSN|[склвритефиледсн](../../../odbc/reference/syntax/sqlwritefiledsn-function.md)|
