---
title: Доступ к определяемым пользователем типам в ADO.NET | Документация Майкрософт
description: Определяемые пользователем типы, написанные на языках .NET Framework CLR, позволяют базе данных SQL Server хранить объекты и пользовательские структуры данных. В ADO.NET поставщик предоставляет определяемые пользователем типы.
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- ADO.NET [CLR integration]
- UDTs [CLR integration], ADO.NET
- user-defined types [CLR integration], ADO.NET
ms.assetid: 4b0d876c-8066-490e-8e18-327c0e942b19
author: rothja
ms.author: jroth
ms.openlocfilehash: cbbff72ab506238ec2134da8a91f91e3a315eb3f
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85727849"
---
# <a name="accessing-user-defined-types-in-adonet"></a>Доступ к определяемым пользователем типам в ADO.NET
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  Определяемые пользователем типы записываются с помощью любого языка, поддерживаемого [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework среде CLR, которая создает проверяемый код. Сюда относятся языки [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# и [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic. Определяемые пользователем типы разрешают сохранять объекты и пользовательские структуры данных в базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Данные представляются как открытые элементы класса или структуры .NET Framework, а поведение определяется методами класса или структуры. Пользовательский тип можно использовать в качестве определения столбца таблицы, переменной в пакете [!INCLUDE[tsql](../../includes/tsql-md.md)], аргумента функции или хранимой процедуры [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
 В ADO.NET поставщик **System. Data. SqlClient** предоставляет определяемые пользователем типы следующими способами:  
  
-   Через **System. Data. SqlClient. SqlDataReader** в качестве объекта.  
  
-   Через **SqlDataReader** как необработанные байты.  
  
-   В качестве параметра объекта **System. Data. SqlClient. SqlParameter** .  
  
## <a name="in-this-section"></a>В этом разделе  
 [Получение данных определяемого пользователем типа](../../relational-databases/clr-integration-database-objects-user-defined-types/accessing-user-defined-types-retrieving-udt-data.md)  
 Описывает, как получить данные определяемого пользователем типа и как указать параметры.  
  
 [Обновление столбцов определяемых пользователем типов с помощью DataAdapter](../../relational-databases/clr-integration-database-objects-user-defined-types/accessing-user-defined-types-updating-udt-columns-with-dataadapters.md)  
 Описывает, как работать с определяемыми пользователем типами в **наборах** данных и как обновлять данные определяемых пользователем типов с помощью **DataAdapter**.  
  
## <a name="see-also"></a>См. также  
 [Определяемые пользователем типы данных CLR](../../relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types.md)  
  
  
