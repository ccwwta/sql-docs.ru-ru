---
description: MSSQLSERVER_2570
title: MSSQLSERVER_2570 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 2570 (Database Engine error)
ms.assetid: 29800aa9-81aa-4371-992c-487dbb617f46
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1d1499a07472f90cd684dfb77638a4c3d7d9a981
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99181005"
---
# <a name="mssqlserver_2570"></a>MSSQLSERVER_2570
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|2570|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|DBCC_COLUMN_VALUE_OUT_OF_RANGE|  
|Текст сообщения|Страница P_ID, область памяти S_ID в идентификаторе объекта O_ID, идентификатор индекса I_ID, идентификатор секции PN_ID, идентификатор единицы распределения A_ID (тип TYPE). Значение столбца COLUMN_NAME вне допустимого диапазона типа данных «DATATYPE». Замените значение столбца на допустимое.|  
  
## <a name="explanation"></a>Объяснение  
Значение указанного столбца выходит за пределы допустимого диапазона возможных значений для типа данных этого столбца.  
  
## <a name="user-action"></a>Действие пользователя  
Исправить ошибку невозможно. Замените значение столбца на допустимое в пределах диапазона для типа данных этого столбца и выполните команду еще раз.  Дополнительные сведения см. в статье базы знаний [923247](https://support.microsoft.com/kb/923247).  
  
## <a name="see-also"></a>См. также:  
[UPDATE (Transact-SQL)](~/t-sql/queries/update-transact-sql.md)  
[Типы данных (Transact-SQL)](~/t-sql/data-types/data-types-transact-sql.md)  
  
