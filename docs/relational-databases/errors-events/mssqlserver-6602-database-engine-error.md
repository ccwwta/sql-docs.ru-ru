---
description: MSSQLSERVER_6602
title: MSSQLSERVER_6602
ms.custom: ''
ms.date: 12/25/2020
ms.prod: sql
ms.reviewer: ramakoni1, pijocoder, suresh-kandoth, vencher, tejasaks, docast
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 6602 (Database Engine error)
ms.assetid: ''
author: suresh-kandoth
ms.author: ramakoni
ms.openlocfilehash: 594898082fb21f712cfb99abfb535aea46b5164d
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100348719"
---
# <a name="mssqlserver_6602"></a>MSSQLSERVER_6602
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

## <a name="details"></a>Сведения

|attribute|Значение|
|---|---|
|Название продукта|SQL Server|
|Идентификатор события|6602|
|Источник события|MSSQLSERVER|
|Компонент|SQLEngine|
|Символическое имя|XMLERR_PARSEERR2|
|Текст сообщения|Описание ошибки: "%.*ls".|
||

## <a name="explanation"></a>Пояснение

Эта ошибка возникает при попытке выполнить хранимую процедуру `sp_xml_preparedocument` в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], где содержимое параметра `xmltext` является сложным XML-документом. При этом пользователь получает сообщение об ошибке такого рода:

> Ошибка синтаксического анализа XML 0x80004005 в строке 1 рядом с текстом XML "\<XML document sample>".  
Сообщение 6602, уровень 16, состояние 2, процедура sp_xml_preparedocument, строка 1.  
Описание ошибки: "Неизвестная ошибка".

## <a name="cause"></a>Причина

Эта проблема возникает из-за ограничений средства синтаксического анализа MSXML (Msxmlsql.dll), которое используется [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].

Она связана не столько с размером XML-документа, сколько с его сложной структурой. Проблема может быть вызвана сочетанием глубины структуры XML-элемента, числа и размера атрибутов, а также количества сущностей в атрибутах. Однако уровень сложности, необходимый для достижения этого ограничения, характерен для XML-документов размером в несколько мегабайт.

## <a name="user-action"></a>Рекомендуемые действия

Чтобы устранить эту проблему, попробуйте упростить структуру XML-документа.

> [!NOTE]
> По возможности не используйте очень большие однострочные атрибуты со множеством сущностей или XML-объектов.
