---
description: Метод Open (объект Connection ADO)
title: Метод Open (подключение ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Connection15::raw_Open
- Connection15::Open
- _Connection::Open
helpviewer_keywords:
- Open method [ADO]
ms.assetid: 663defab-5545-4973-9036-24d5882c9737
author: rothja
ms.author: jroth
ms.openlocfilehash: a3bca1379c776f6fad1f4ab2aa7368b424ff9e7f
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99170709"
---
# <a name="open-method-ado-connection"></a>Метод Open (объект Connection ADO)
Открывает соединение с источником данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
connection.Open ConnectionString, UserID, Password, Options  
```  
  
#### <a name="parameters"></a>Параметры  
 *ConnectionString*  
 Необязательный параметр. **Строковое** значение, содержащее сведения о соединении. Сведения о допустимых параметрах см. в свойстве [ConnectionString](./connectionstring-property-ado.md) .  
  
 *UserID*  
 Необязательный параметр. **Строковое** значение, содержащее имя пользователя, используемое при установлении соединения.  
  
 *Пароль*  
 Необязательный параметр. **Строковое** значение, содержащее пароль, используемый при установлении соединения.  
  
 *Параметры*  
 Необязательный параметр. Значение [коннектоптионенум](./connectoptionenum.md) , которое определяет, должен ли этот метод возвращаться после (синхронно) или до (асинхронно) установления соединения.  
  
## <a name="remarks"></a>Замечания  
 Использование метода **Open** для объекта [Connection](./connection-object-ado.md) устанавливает физическое соединение с источником данных. После успешного завершения этого метода подключение будет активно, и вы сможете выполнить команды для него и обработать результаты.  
  
 Используйте необязательный аргумент *ConnectionString* , чтобы указать либо строку подключения, содержащую последовательность *аргументов аргумента* *= значение* , разделенную точкой с запятой, либо файл или ресурс каталога, определенный с помощью URL-адреса. Свойство **ConnectionString** автоматически наследует значение, используемое для аргумента *ConnectionString* . Поэтому можно либо задать свойство **ConnectionString** объекта **соединения** перед его открытием, либо использовать аргумент *ConnectionString* для задания или переопределения текущих параметров соединения во время вызова метода **Open** .  
  
 При передаче сведений о пользователях и паролях в аргументе *ConnectionString* и в необязательных *аргументах* *UserID* и Password аргументы *UserID* и *Password* переопределят значения, указанные в *ConnectionString*.  
  
 Когда вы завершите операции с открытым **подключением**, используйте метод [Close](./close-method-ado.md) , чтобы освободить все связанные системные ресурсы. Закрытие объекта не приводит к его удалению из памяти; Вы можете изменить его параметры свойств и открыть его позже с помощью метода **Open** . Чтобы полностью исключить объект из памяти, присвойте переменной объекта значение *Nothing*.  
  
> [!NOTE]
>  **Использование удаленной службы данных** При использовании объекта **подключения** на стороне клиента метод **Open** не устанавливает соединение с сервером до тех пор, пока в объекте **Connection** не будет открыт [набор записей](./recordset-object-ado.md) .  
  
> [!NOTE]
>  URL-адреса, использующие схему HTTP, автоматически вызывают [поставщик OLE DB Майкрософт для публикации в Интернете](../../guide/appendixes/microsoft-ole-db-provider-for-internet-publishing.md). Дополнительные сведения см. в разделе [абсолютные и относительные URL-адреса](../../guide/data/absolute-and-relative-urls.md).  
  
## <a name="applies-to"></a>Применение  
 [Объект Connection (ADO)](./connection-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Примеры методов Open и Close (Visual Basic)](./open-and-close-methods-example-vb.md)   
 [Пример методов Open и Close (VBScript)](./open-and-close-methods-example-vbscript.md)   
 [Пример методов Open и Close (Visual c++)](./open-and-close-methods-example-vc.md)   
 [Метод Open (запись ADO)](./open-method-ado-record.md)   
 [Метод Open (набор записей ADO)](./open-method-ado-recordset.md)   
 [Метод Open (поток ADO)](./open-method-ado-stream.md)   
 [Метод OpenSchema](./openschema-method.md)