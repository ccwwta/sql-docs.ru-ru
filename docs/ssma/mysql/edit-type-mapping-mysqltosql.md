---
description: Изменение сопоставления типов (MySQLToSQL)
title: Изменение сопоставления типов (MySQLToSQL) | Документация Майкрософт
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 184f7ab2-725f-491e-a15b-b889f2fb6a68
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: b1ddf264835cf0a9a008335787353d7a1051431f
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100016604"
---
# <a name="edit-type-mapping-mysqltosql"></a>Изменение сопоставления типов (MySQLToSQL)
Диалоговое окно **Изменение сопоставления типов** позволяет указать, как типы сопоставляются между исходным и целевым объектами базы данных.  
  
Доступ к этому диалоговому окну можно получить в нескольких местах:  
  
-   При выборе базы данных-источника или объекта базы данных справа от обозревателя метаданных появляется вкладка **Сопоставление типов** . Нажмите кнопку **Добавить** , чтобы добавить новое сопоставление типов, или кнопку **изменить** , чтобы изменить существующее сопоставление типов.  
  
-   В меню **Сервис** выберите пункт **Параметры проекта** или **Параметры проекта по умолчанию**. В появившемся диалоговом окне выберите **Сопоставление типов**. Нажмите кнопку **Добавить** , чтобы добавить новое сопоставление типов, или кнопку **изменить** , чтобы изменить существующее сопоставление типов.  
  
-   Сопоставления типов, связанных с таблицами, переопределяют сопоставления типов базы данных и проекта. Сопоставления, зависящие от базы данных, переопределяют сопоставления проектов.  
  
## <a name="options"></a>Параметры  
  
##### <a name="source-type"></a>Тип исходного значения  
Выберите тип данных источника для соотнесения с типом данных SQL Server.  
  
Если тип данных имеет переменную длину, в разделе **sourceType** будут отображаться следующие поля:  
  
##### <a name="from"></a>От  
Укажите минимальную длину для этого сопоставления. Например, для типа данных **nchar** можно ввести значение 10, чтобы указать, что это сопоставление предназначено для диапазона, начиная с **nchar (10).**  
  
##### <a name="to"></a>Кому  
Укажите максимальную длину для этого сопоставления. Например, для типа данных **nchar** можно ввести значение 20, чтобы указать, что это сопоставление относится к диапазону, завершающему значение **nchar (20).**  
  
##### <a name="target-type"></a>Тип результирующего значения  
Выберите тип данных SQL Server, с которым сопоставлен исходный тип данных. Когда SSMA создает таблицу или в SQL Server, исходный тип данных изменится на этот тип данных.  
  
Если тип данных имеет переменную длину, в разделе **целевой тип** появится следующее поле:  
  
##### <a name="replace-with"></a>Заменить на  
Укажите целевую длину для этого сопоставления. Например, для типа данных **nvarchar** можно ввести значение 20, чтобы указать, что указанный исходный тип данных должен быть сопоставлен с типом **nvarchar (20).**  
  
