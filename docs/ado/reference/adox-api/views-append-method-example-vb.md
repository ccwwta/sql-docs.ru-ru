---
description: Пример метода Append коллекции Views (Visual Basic)
title: Пример метода Append для представлений (Visual Basic) | Документация Майкрософт
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
- Append method [ADOX]
ms.assetid: b5b4c082-ac29-4f49-a8b8-e21b554c9b0d
author: rothja
ms.author: jroth
ms.openlocfilehash: 1cc2df470b2b51176cd44433359cf74d31c36863
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100053385"
---
# <a name="views-append-method-example-vb"></a>Пример метода Append коллекции Views (Visual Basic)
В следующем коде показано, как использовать объект [Command](../ado-api/command-object-ado.md) и метод [append](./append-method-adox-views.md) коллекции [views](./views-collection-adox.md) для создания нового представления в базовом источнике данных.  
  
```  
' BeginCreateViewVB  
Sub Main()  
    On Error GoTo CreateViewError  
  
    Dim cmd As New ADODB.Command  
    Dim cat As New ADOX.Catalog  
  
    ' Open the Catalog  
    cat.ActiveConnection = _  
        "Provider='Microsoft.Jet.OLEDB.4.0';" & _  
        "Data Source='Northwind.mdb';"  
  
    ' Create the command representing the view.  
    cmd.CommandText = "Select * From Customers"  
  
    ' Create the new View  
    cat.Views.Append "AllCustomers", cmd  
  
    'Clean up  
    Set cat.ActiveConnection = Nothing  
    Set cat = Nothing  
    Set cmd = Nothing  
    Exit Sub  
  
CreateViewError:  
  
    Set cat = Nothing  
    Set cmd = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
End Sub  
' EndCreateViewVB  
```  
  
## <a name="see-also"></a>См. также:  
 [Свойство ActiveConnection (ADOX)](./activeconnection-property-adox.md)   
 [Метод Append (представления ADOX)](./append-method-adox-views.md)   
 [Объект каталога (ADOX)](./catalog-object-adox.md)   
 [Объект View (ADOX)](./view-object-adox.md)   
 [Коллекция Views (ADOX)](./views-collection-adox.md)