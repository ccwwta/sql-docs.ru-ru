---
description: Команда SET UNIQUE
title: ЗАДАТЬ УНИКАЛЬную команду | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- SET UNIQUE command [ODBC]
ms.assetid: 1f69e31e-4599-47cc-ac89-b86fba8703c5
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: f30e589349ab1f0388e43af0aec132465b1fcdce
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99208585"
---
# <a name="set-unique-command"></a>Команда SET UNIQUE
Указывает, сохраняются ли записи с повторяющимися значениями ключа индекса в файле индекса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
SET UNIQUE ON | OFF  
```  
  
## <a name="arguments"></a>Аргументы  
 ON  
 Указывает, что любая запись с повторяющимися значениями ключа индекса не должна включаться в файл индекса. В файл индекса включаются только первая запись с исходным значением ключа индекса.  
  
 OFF  
 (По умолчанию.) Указывает, что в файл индекса будут включаться записи с повторяющимися значениями ключа индекса.  
  
## <a name="remarks"></a>Замечания  
 При повторном ИНДЕКСИРОВАНии файл индекса остается установленным уникальным параметром SET UNIQUE. Дополнительные сведения см. в разделе [index](../../odbc/microsoft/index-command.md).
