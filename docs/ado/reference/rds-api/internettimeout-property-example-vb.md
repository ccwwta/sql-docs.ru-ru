---
description: Пример свойства InternetTimeout (Visual Basic)
title: Пример свойства InternetTimeout (Visual Basic) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- InternetTimeout property [ADO], Visual Basic example
ms.assetid: b35d2f4a-449c-4170-aab6-9ff88c890043
author: rothja
ms.author: jroth
ms.openlocfilehash: a3cc6ad7775494fe308c37e79b841dfaa6dc5a8f
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100049374"
---
# <a name="internettimeout-property-example-vb"></a>Пример свойства InternetTimeout (Visual Basic)
> [!IMPORTANT]
>  Начиная с Windows 8 и Windows Server 2012, компоненты RDS больше не включены в операционную систему Windows (Дополнительные сведения см. в статье о совместимости Windows 8 и [Windows server 2012 Cookbook](https://www.microsoft.com/download/details.aspx?id=27416) ). Клиентские компоненты RDS будут удалены в следующей версии Windows. Избегайте использования этого компонента в новых разработках и запланируйте изменение существующих приложений, в которых он применяется. Приложения, использующие RDS, должны переноситься в [службу данных WCF](/dotnet/framework/wcf/).  
  
 В этом примере демонстрируется свойство [InternetTimeout](./internettimeout-property-rds.md) , которое существует в объектах « [элемент управления](./datacontrol-object-rds.md) данным» и « [пространство](./dataspace-object-rds.md) ». В этом примере используется объект **элемента управления** DataObject и устанавливается время ожидания равным 20 секундам.  
  
```  
'BeginInternetTimeoutVB  
  
Public Sub Main()  
    On Error GoTo ErrorHandler  
  
    Dim dc As RDS.DataControl  
    Dim rst As ADODB.Recordset  
    Set dc = New RDS.DataControl  
  
    dc.Server = "https://MyServer"  
    dc.ExecuteOptions = 1  
    dc.FetchOptions = 1  
    dc.Connect = "Provider='sqloledb';Data Source='MySqlServer';" & _  
        "Initial Catalog='Pubs';Integrated Security='SSPI';"  
    dc.SQL = "SELECT * FROM Authors"  
     ' Wait at least 20 seconds  
    dc.InternetTimeout = 200  
  
    dc.Refresh  
     ' Use another Recordset as a convenience  
    Set rst = dc.Recordset  
    Do While Not rst.EOF  
       Debug.Print rst!au_fname & " " & rst!au_lname  
       rst.MoveNext  
    Loop  
  
    If rst.State = adStateOpen Then rst.Close  
    Set rst = Nothing  
    Set dc = Nothing  
    Exit Sub  
  
ErrorHandler:  
    ' clean up  
    If Not rst Is Nothing Then  
        If rst.State = adStateOpen Then rst.Close  
    End If  
    Set rst = Nothing  
    Set dc = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
  
End Sub  
'EndInternetTimeoutVB  
```  
  
## <a name="see-also"></a>См. также:  
 [Объект элемента управления (RDS)](./datacontrol-object-rds.md)   
 [Объект Space (RDS)](./dataspace-object-rds.md)   
 [Свойство InternetTimeout (служба удаленных рабочих столов)](./internettimeout-property-rds.md)