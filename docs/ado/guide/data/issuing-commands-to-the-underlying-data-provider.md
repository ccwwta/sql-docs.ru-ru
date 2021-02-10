---
description: Выдача команды для базового поставщика данных
title: Выдача команд базовому поставщику данных | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- shape commands [ADO]
- underlying providers [ADO]
- data shaping [ADO], commands
ms.assetid: d6001863-7733-4c32-817f-081e48587fa1
author: rothja
ms.author: jroth
ms.openlocfilehash: c01178c70a0e6a9e049f9fcfbc0a584fa5fa7ef0
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100032746"
---
# <a name="issuing-commands-to-the-underlying-data-provider"></a>Выдача команды для базового поставщика данных
Любая команда, которая не начинается с SHAPE, передается поставщику данных. Это эквивалентно выдаче команды Shape в виде "SHAPE {поставщик команда}". Этим командам *не* требуется создавать **набор записей**. Например, форма {DROP TABLE MyTable} является абсолютно допустимой командой Shape, предполагая, что поставщик данных поддерживает инструкцию DROP TABLE.  
  
 Эта возможность позволяет использовать как обычные команды поставщика, так и команды Shape для совместного использования одного соединения и транзакции.  
  
## <a name="see-also"></a>См. также:  
 [Пример формирования данных](./data-shaping-example.md)   
 [Грамматика формальной фигуры](./formal-shape-grammar.md)   
 [Общие сведения о командах формирования данных](./shape-commands-in-general.md)