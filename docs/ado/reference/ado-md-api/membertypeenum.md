---
description: MemberTypeEnum
title: Мембертипинум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- MemberTypeEnum
helpviewer_keywords:
- MemberTypeEnum enumeration [ADO MD]
ms.assetid: 5d8132c0-7ca2-4f86-8336-1b34213869ad
author: rothja
ms.author: jroth
ms.openlocfilehash: b83747edabc12f2f84d728a456255513ee1f0f66
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100051085"
---
# <a name="membertypeenum"></a>MemberTypeEnum
Задает параметр для свойства [Type](./type-property-ado-md.md) объекта- [члена](./member-object-ado-md.md) .  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**adMemberAll**|4|Указывает, что объект **member** представляет все элементы уровня.|  
|**adMemberFormula**|3|Указывает, что объект- **член** вычисляется с помощью выражения формулы.|  
|**adMemberMeasure**|2|Указывает, что объект- **член** принадлежит измерению Measures и представляет количественный атрибут.|  
|**adMemberRegular**|1|По умолчанию. Указывает, что объект **member** представляет экземпляр бизнес-сущности.|  
|**adMemberUnknown**|0|Не удается определить тип элемента.|