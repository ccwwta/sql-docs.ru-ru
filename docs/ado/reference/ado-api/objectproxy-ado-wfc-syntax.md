---
description: ObjectProxy (ADO — синтаксис WFC)
title: Обжектпрокси (ADO — синтаксис WFC) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
helpviewer_keywords:
- ObjectProxy collection [ADO]
ms.assetid: f68f58bc-ad28-46cc-9fb3-099e1a678397
author: rothja
ms.author: jroth
ms.openlocfilehash: 3d88c2ccdc74a9bb833ad831ea6a0b31cf02397b
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100041484"
---
# <a name="objectproxy-ado---wfc-syntax"></a>ObjectProxy (ADO — синтаксис WFC)
Объект **обжектпрокси** представляет сервер и возвращается методом **CreateObject** объекта [пространства](../rds-api/dataspace-object-rds.md) данных. Класс Обжектпрокси имеет один метод, **Call**, который может вызывать метод на сервере и возвращать объект, полученный в результате этого вызова.  
  
 **упаковать com. MS. WFC. Data**  
  
## <a name="methods"></a>Методы  
  
### <a name="call-method-adowfc-syntax"></a>Метод Call (синтаксис ADO/WFC)  
 Вызывает метод на сервере, представленном Обжектпрокси. При необходимости аргументы метода могут передаваться как массив объектов.  
  
#### <a name="syntax"></a>Синтаксис  
  
```  
public Object ObjectProxy.( String method )  
public Object ObjectProxy.( String method, Object[] args)  
```  
  
#### <a name="returns"></a>Возвращаемое значение  
 Объект  
 Объект, являющийся результатом вызова метода.  
  
#### <a name="parameters"></a>Параметры  
 *обжектпрокси*  
 Объект **обжектпрокси** , представляющий сервер.  
  
 *Method*  
 Строка, содержащая имя метода, который необходимо вызвать на сервере.  
  
 *args*  
 Необязательный элемент. Массив объектов, являющихся аргументами метода на сервере. Типы данных Java автоматически преобразуются в типы данных, подходящие для использования на сервере.