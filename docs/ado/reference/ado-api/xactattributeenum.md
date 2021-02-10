---
description: XactAttributeEnum
title: Ксактаттрибутинум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- XactAttributeEnum
helpviewer_keywords:
- XactAttributeEnum enumeration [ADO]
ms.assetid: e7dcecd3-7dc7-445c-b922-f700c3067fbc
author: rothja
ms.author: jroth
ms.openlocfilehash: e741ec0e5458218ddb6dc3a46c3a098acf482611
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100056029"
---
# <a name="xactattributeenum"></a>XactAttributeEnum
Задает атрибуты транзакции для объекта [соединения](./connection-object-ado.md) .  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**адксактабортретаининг**|262144|Выполняет сохранность прерываний, вызывая [RollbackTrans](./begintrans-committrans-and-rollbacktrans-methods-ado.md) для автоматического запуска новой транзакции. Не все поставщики поддерживают такое поведение.|  
|**адксакткоммитретаининг**|131072|Сохраняет фиксации, вызывая [CommitTrans](./begintrans-committrans-and-rollbacktrans-methods-ado.md) для автоматического запуска новой транзакции. Не все поставщики поддерживают такое поведение.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com. MS. WFC. Data**  
  
|Константа|  
|--------------|  
|Адоенумс. Ксактаттрибуте. АБОРТРЕТАИНИНГ|  
|Адоенумс. Ксактаттрибуте. КОММИТРЕТАИНИНГ|  
  
## <a name="applies-to"></a>Применение  
 [Свойство Attributes (ADO)](./attributes-property-ado.md)