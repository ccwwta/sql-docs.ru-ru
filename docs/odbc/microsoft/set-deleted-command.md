---
description: Команда SET DELETED
title: ЗАДАТЬ УДАЛЕНную команду | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- SET DELETED command [ODBC]
ms.assetid: 6b5e0086-156d-471d-8e7f-6c5fa9686cd5
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 6447e2d0c77e1a161df58ca070fae8c624c196a8
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99208642"
---
# <a name="set-deleted-command"></a>Команда SET DELETED
Указывает, обрабатываются ли записи, помеченные для удаления, и доступны ли они для использования в других командах.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
SET DELETED ON | OFF  
```  
  
## <a name="arguments"></a>Аргументы  
 ON  
 (Значение по умолчанию для драйвера; значение по умолчанию для Visual FoxPro — OFF.) Указывает, что команды, работающие с записями (включая записи в связанных таблицах) с использованием области, игнорируют записи, помеченные для удаления.  
  
 OFF  
 Указывает, что к записям, помеченным для удаления, могут обращаться команды, работающие с записями (включая записи в связанных таблицах) с использованием области.  
  
## <a name="remarks"></a>Замечания  
 Запросы, использующие DELETEd () для проверки состояния записей, можно оптимизировать с помощью технологии Visual FoxPro Рушморе, если таблица индексируется по УДАЛЕНному ().  
  
> [!IMPORTANT]  
>  Параметр SET DELETEd игнорируется, если областью действия по умолчанию для команды является текущая запись или если вы включаете область одной записи. Параметр INDEX всегда игнорирует SET DELETEed и индексирует все записи в таблице.  
  
## <a name="see-also"></a>См. также:  
 [DELETE (команда SQL)](../../odbc/microsoft/delete-sql-command.md)
