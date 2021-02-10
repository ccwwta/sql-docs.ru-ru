---
description: Поставщики данных
title: Поставщики данных | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- data providers [ADO]
- OLE DB providers [ADO]
- ADO, OLE DB providers
ms.assetid: 877b9f25-60c4-4ab6-8052-2c28a3849e89
author: rothja
ms.author: jroth
ms.openlocfilehash: 67abe2bd8d2af4e43b1f6d14aed6588b9ddd7a2e
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100033312"
---
# <a name="data-providers"></a>Поставщики данных
Поставщики данных представляют различные источники данных, такие как базы данных SQL, индексированные последовательные файлы, электронные таблицы, хранилища документов и файлы почты. Поставщики предоставляют данные единообразно, используя общую абстракцию, которая называется набором строк.  
  
 ADO является мощным и гибким средством, поскольку может подключаться к любому из нескольких разных поставщиков данных и по-прежнему предоставлять ту же модель программирования независимо от конкретных функций любого поставщика. Однако, поскольку каждый поставщик данных уникален, взаимодействие приложения с ADO зависит от поставщика данных.  
  
 Например, возможности и возможности поставщика OLE DB для SQL Server, который используется для доступа к базам данных Microsoft SQL Server, значительно отличается от поставщика Microsoft OLE DB для публикации в Интернете, который используется для доступа к хранилищам файлов на веб-сервере.
