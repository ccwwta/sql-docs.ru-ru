---
description: Команда SET EXCLUSIVE
title: Задание МОНОПОЛЬной команды | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- SET EXCLUSIVE command [ODBC]
ms.assetid: d4fe12c5-7e8b-4d20-9ea4-2bcaffb271f2
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 43cd58e5e9f714de0defe36cea020ccb96ac3efa
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99208628"
---
# <a name="set-exclusive-command"></a>Команда SET EXCLUSIVE
Указывает, следует ли открывать файлы таблиц для монопольного или общего использования в сети.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
SET EXCLUSIVE ON | OFF  
```  
  
## <a name="arguments"></a>Аргументы  
 ON  
 Ограничивает доступность таблицы, открытой в сети, пользователю, открывшему ее. Таблица недоступна другим пользователям в сети. SET EXCLUSIVE ON также запрещает другим пользователям доступ только для чтения.  
  
 OFF  
 (Значение по умолчанию для драйвера; значения по умолчанию для Visual FoxPro включены для сеанса глобальных данных и ОТКЛЮЧЕНы для сеанса закрытых данных.) Разрешает совместное открытие и изменение таблицы, открытой в сети любым пользователем в сети.  
  
## <a name="remarks"></a>Замечания  
 Изменение параметра SET EXCLUSIVE не приводит к изменению состояния ранее открытых таблиц. Например, если таблица открыта с параметром SET EXCLUSIVE, установленным в ON, а SET EXCLUSIVE в дальнейшем изменяется на OFF, то в таблице сохраняется состояние монопольного использования.  
  
## <a name="see-also"></a>См. также:  
 [Диалоговое окно настройки ODBC для Visual FoxPro](../../odbc/microsoft/odbc-visual-foxpro-setup-dialog-box.md)
