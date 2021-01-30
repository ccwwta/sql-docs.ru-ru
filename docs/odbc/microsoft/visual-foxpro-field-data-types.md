---
description: Типы данных полей Visual FoxPro
title: Типы данных поля Visual FoxPro | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- field data types [ODBC]
- Visual FoxPro ODBC driver [ODBC], data types
ms.assetid: 50b733dc-679a-4b10-bc5d-98bb474dead2
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 2032ee25039364186f33486e4662b84c36c06947
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99207478"
---
# <a name="visual-foxpro-field-data-types"></a>Типы данных полей Visual FoxPro
В следующей таблице перечислены значения аргумента *FieldType* в инструкции ALTER table и CREATE TABLE и указано, требуются ли аргументы *нфиелдвидс* и *нпреЦисион* .  
  
|*FieldType*|*нфиелдвидс*|*нпреЦисион*|Описание|  
|-----------------|-------------------|------------------|-----------------|  
|B|-|d|Double|  
|C|Нет|-|Символьное поле ширины *n*|  
|D|-|-|Дата|  
|F|Нет|d|Плавающее числовое поле Width *n* с *d* десятичными разрядами|  
|G|-|-|Общие сведения|  
|I|-|-|Целое число|  
|L|-|-|Логические|  
|M|-|-|Memo|  
|Нет|Нет|d|Числовое поле ширины *n* с *d* десятичными разрядами|  
|T|-|-|Дата и время|  
|Да|-|-|Валюта|
