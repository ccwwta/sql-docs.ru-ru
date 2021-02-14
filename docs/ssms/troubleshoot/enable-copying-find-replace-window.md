---
description: 'Обходное решение для включения копирования в окне поиска и замены '
title: Включение копирования в окне поиска и замены
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
ms.assetid: c28ffa44-7b8b-4efa-b755-c7a3b1c11ce4
author: dzsquared
ms.author: drskwier
ms.reviewer: maghan, sstein
ms.custom: seo-lt-2019
ms.date: 11/03/2020
ms.openlocfilehash: f7a11c952fa20b720ad37abc204c7dbb31f0e96f
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100058609"
---
# <a name="workaround-to-enable-copying-from-find-and-replace-window"></a>Обходное решение для включения копирования в окне поиска и замены

[!INCLUDE[Applies to](../../includes/appliesto-ss-asdb-asdw-xxx-md.md)]

Для включение копирования из окна поиска и замены необходимо обходное решение.  Если вы видите, что не удается выполнить копирование из окна поиска и замена в SQL Server Management Studio, следуйте [обходному решению](#workaround) ниже.

## <a name="error-message"></a>Сообщение об ошибке

При попытке скопировать текст из окна поиска и замены в SQL Server Management Studio появляется сообщение об ошибке.

> Несохраненные документы не могут быть вырезаны или скопированы в буфер обмена из различных проектов файлов. Перед вырезанием или копированием несохраненных документов необходимо сохранить их.

![Диалоговое окно ошибки для: Несохраненные документы не могут быть вырезаны или скопированы в буфер обмена из различных проектов файлов. Перед вырезанием или копированием несохраненных документов необходимо сохранить их.](../media/troubleshoot/unable-copy-find-replace-window.png)

## <a name="workaround"></a>Обходной путь

Чтобы включить копирование текста из окна поиска и замены, выполните следующие действия.

1. В меню **Средства** откройте **Параметры**.

2. В разделе **Среда**>**Документы** снимите флажок для пункта "Показывать прочие файлы в обозревателе решений".

3. Закройте и снова откройте среду SQL Server Management Studio.

![Окно параметров со снятым флажком "Показывать прочие файлы в обозревателе решений".](../media/troubleshoot/fix-copy-find-replace-window.png)

