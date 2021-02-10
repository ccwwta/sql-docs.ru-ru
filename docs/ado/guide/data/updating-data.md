---
description: Обновление данных
title: Обновление данных | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- data updates [ADO], about data updates
- updating data [ADO], about updating data
ms.assetid: 6508e4e9-e33a-4dad-b340-5d632fd78a91
author: rothja
ms.author: jroth
ms.openlocfilehash: 3cbeb2bf63414f1b07912dcc0a4cc5b78ec3656e
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100036916"
---
# <a name="updating-data"></a>Обновление данных
Поведение и функциональность обновления во многом зависят от режима обновления (типа блокировки), типа курсора и положения курсора.  
  
 Используйте метод **Update** , чтобы сохранить изменения, внесенные в текущую запись объекта **Recordset** с момента вызова метода **AddNew** или путем изменения любых значений полей в существующей записи. Объект **набора записей** должен поддерживать обновления.  
  
 Если объект **Recordset** поддерживает пакетное обновление, можно кэшировать несколько изменений в одной или нескольких записях локально, пока не будет вызван метод **UpdateBatch** . Если вы изменяете текущую запись или добавляете новую запись при вызове метода **UpdateBatch** , ADO автоматически вызывает метод **Update** , чтобы сохранить все ожидающие изменения в текущей записи перед передачей пакетных изменений поставщику.  
  
 Текущая запись остается текущей после вызова методов **Update** или **UpdateBatch** .  
  
 Этот раздел содержит следующие подразделы.  
  
-   [Режим интерпретации](../../../ado/guide/data/immediate-mode.md)  
  
-   [Пакетный режим](../../../ado/guide/data/batch-mode.md)  
  
-   [Обработка транзакций](../../../ado/guide/data/transaction-processing.md)
