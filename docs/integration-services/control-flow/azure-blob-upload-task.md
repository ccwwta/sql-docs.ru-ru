---
description: Задача передачи больших двоичных объектов Azure
title: Задача передачи больших двоичных объектов Azure | Документы Майкрософт
ms.custom: ''
ms.date: 05/22/2019
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql13.dts.designer.afpblobuptask.f1
- sql14.dts.designer.afpblobuptask.f1
ms.assetid: 6ea068b0-4cd8-45b5-b89d-09b8f25040c0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 588bb693d5bcf8561d7f697dc910c483d63160a7
ms.sourcegitcommit: 2f3f5920e0b7a84135c6553db6388faf8e0abe67
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98783085"
---
# <a name="azure-blob-upload-task"></a>Задача передачи больших двоичных объектов Azure

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


**Задача передачи BLOB-объектов Azure** позволяет пакету служб SSIS передавать файлы в хранилище BLOB-объектов Azure.
    
Чтобы добавить **задачу передачи BLOB-объектов Azure**, перетащите ее в конструктор служб SSIS и дважды щелкните или щелкните правой кнопкой мыши, а затем выберите **Изменить** , чтобы открыть диалоговое окно **Редактор задач передачи BLOB-объектов Azure** .  
  
 **Задача передачи больших двоичных объектов Azure** входит в состав [пакета дополнительных компонентов SQL Server Integration Services (SSIS) для Azure](../../integration-services/azure-feature-pack-for-integration-services-ssis.md).
  
 Следующая таблица содержит описания полей этого диалогового окна.  

|**Поле**|**Описание**|  
|---|---|  
|AzureStorageConnection|Создайте новый или укажите существующий диспетчер подключений службы хранилища Azure, который ссылается на учетную запись хранения Azure, указывающую на место размещения файлов BLOB-объектов.|  
|BlobContainer|Задает имя контейнера BLOB-объектов, который содержит загруженные файлы в виде больших двоичных объектов.|  
|BlobDirectory|Указывает каталог больших двоичных объектов, где загруженный файл хранится в виде блочного BLOB-объекта. Каталог больших двоичных объектов — это виртуальная иерархическая структура. Если большой двоичный объект уже существует, он заменяется.|  
|LocalDirectory|Укажите локальный каталог, который содержит файлы для отправки.|  
|SearchRecursively|Указывает, следует ли выполнять рекурсивный поиск в подкаталогах.|  
|FileName|Указывает имя фильтра для выбора файлов с указанным шаблоном имени. Например, `MySheet*.xls\*` включает такие файлы, как `MySheet001.xls` и `MySheetABC.xlsx`.|  
|TimeRangeFrom/TimeRangeTo|Задает фильтр диапазона времени. Включаются файлы, измененные после **TimeRangeFrom** и до **TimeRangeTo**.|  
