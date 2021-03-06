---
description: Функция ConfigDriver
title: Функция Конфигдривер | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- ConfigDriver
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- ConfigDriver
helpviewer_keywords:
- ConfigDriver [ODBC]
ms.assetid: 9473f48f-bcae-4784-89c1-7839bad4ed13
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 5abe589b84eff738aeaf41139082781254fb0488
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99174742"
---
# <a name="configdriver-function"></a>Функция ConfigDriver
**Соответствия**  
 Введенная версия: ODBC 2,5  
  
 **Сводка**  
 **Конфигдривер** позволяет программе установки выполнять функции установки и удаления, не требуя от программы вызова **ConfigDSN**. Эта функция выполняет функции конкретного драйвера, такие как создание специфических для драйвера системных сведений и выполнение преобразований DSN во время установки, а также удаление изменений сведений о системе во время удаления. Эта функция предоставляется библиотекой DLL установки драйвера или отдельной библиотекой DLL установки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
  
BOOL ConfigDriver(  
      HWND    hwndParent,  
      WORD    fRequest,  
      LPCSTR  lpszDriver,  
      LPCSTR  lpszArgs,  
      LPSTR   lpszMsg,  
      WORD    cbMsgMax,  
      WORD *  pcbMsgOut);  
```  
  
## <a name="arguments"></a>Аргументы  
 *хвндпарент*  
 Входной Маркер родительского окна. Функция не отображает никакие диалоговые окна, если этот маркер имеет значение null.  
  
 *фрекуест*  
 Входной Тип запроса. Аргумент *фрекуест* должен содержать одно из следующих значений:  
  
 ODBC_INSTALL_DRIVER: Установите новый драйвер.  
  
 ODBC_REMOVE_DRIVER: Удалите драйвер.  
  
 Этот параметр также может быть специфичным для драйвера. в этом случае аргумент *фрекуест* для первого параметра должен начинаться с ODBC_CONFIG_DRIVER_MAX + 1. Аргумент *фрекуест* для любого дополнительного параметра также должен начинаться с значения, превышающего ODBC_CONFIG_DRIVER_MAX + 1.  
  
 *лпсздривер*  
 Входной Имя драйвера, зарегистрированное в Odbcinst.ini ключе сведений о системе.  
  
 *лпсзаргс*  
 Входной Строка, завершающаяся нулем, содержащая аргументы для *фрекуест* конкретного драйвера.  
  
 *лпсзмсг*  
 Проверки Строка, заканчивающаяся нулем и содержащая выходное сообщение от настройки драйвера.  
  
 *кбмсгмакс*  
 Входной Длина *лпсзмсг*.  
  
 *пкбмсгаут*  
 Проверки Общее число байт, доступных для возврата в *лпсзмсг*.  
  
 Если число возвращаемых байт больше или равно *кбмсгмакс*, то выходное сообщение в *лпсзмсг* усекается до *кбмсгмакс* минус символ завершения null. Аргумент *пкбмсгаут* может быть пустым указателем.  
  
## <a name="returns"></a>Возвращаемое значение  
 Функция возвращает TRUE, если она успешна, и FALSE в случае сбоя.  
  
## <a name="diagnostics"></a>Диагностика  
 Когда **конфигдривер** возвращает значение false, связанное значение *\* пферроркоде* отправляется в буфер ошибок установщика путем вызова **склпостинсталлереррор** и может быть получен вызовом **склинсталлереррор**. В следующей таблице перечислены значения *\* пферроркоде* , которые могут быть возвращены **склинсталлереррор** , и объясняется каждый из них в контексте этой функции.  
  
|*\*пферроркоде*|Ошибка|Описание|  
|---------------------|-----------|-----------------|  
|ODBC_ERROR_INVALID_HWND|Недопустимый маркер окна|Недопустимый аргумент *хвндпарент* .|  
|ODBC_ERROR_INVALID_REQUEST_TYPE|Недопустимый тип запроса|Аргумент *фрекуест* не является одним из следующих:<br /><br /> ODBC_INSTALL_DRIVER ODBC_REMOVE_DRIVER<br /><br /> Параметр, относящийся к драйверу, меньше или равен ODBC_CONFIG_DRIVER_MAX.|  
|ODBC_ERROR_INVALID_NAME|Недопустимое имя драйвера или транслятора|Недопустимый аргумент *лпсздривер* . Не удалось найти его в реестре.|  
|ODBC_ERROR_REQUEST_FAILED|Сбой *запроса*|Не удалось выполнить операцию, запрошенную аргументом *фрекуест* .|  
|ODBC_ERROR_DRIVER_SPECIFIC|Ошибка, относящаяся к драйверу или транслятору|Ошибка конкретного драйвера, для которой не определена Ошибка установщика ODBC. Аргумент *сзеррор* в вызове функции **склпостинсталлереррор** должен содержать сообщение об ошибке конкретного драйвера.|  
  
## <a name="comments"></a>Комментарии  
  
### <a name="driver-specific-options"></a>Параметры Driver-Specific  
 Приложение может запрашивать связанные с драйвером функции, предоставляемые драйвером, с помощью аргумента *фрекуест* . *Фрекуест* для первого параметра будет ODBC_CONFIG_DRIVER_MAX плюс 1, а дополнительные параметры будут увеличены на 1 из этого значения. Все аргументы, необходимые драйверу для этой функции, должны быть предоставлены в строке, завершающейся нулем, передаваемой в аргументе *лпсзаргс* . Драйверы, обеспечивающие такую функциональность, должны поддерживать таблицу параметров, относящихся к драйверу. Параметры должны быть полностью документированы в документации по драйверам. Разработчики приложений, которые используют параметры, относящиеся к драйверу, должны учитывать, что это сделает приложение менее совместимым.  
  
### <a name="messages"></a>Сообщения  
 Подпрограмма установки драйвера может отправить текстовое сообщение в приложение в виде строки, завершающейся нулем, в буфере *лпсзмсг* . Сообщение будет обрезано до *кбмсгмакс* минус символ завершения, равный NULL функцией **конфигдривер** , если он больше или равен *кбмсгмакс* символов.
