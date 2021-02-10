---
description: Пример метода Delete коллекции Procedures (Visual Basic)
title: Пример метода Delete процедур (Visual Basic) | Документация Майкрософт
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
- Delete method [ADOX], Visual Basic example
ms.assetid: 94f1ac93-e778-4a40-a85e-94bce5316ac7
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ba7cd56544e1bb7a171e864b908a7ffdacbf093
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100049804"
---
# <a name="procedures-delete-method-example-vb"></a>Пример метода Delete коллекции Procedures (Visual Basic)
В следующем коде показано, как удалить процедуру с помощью метода [Delete](./delete-method-adox-collections.md) в коллекции [процедур](./procedures-collection-adox.md) .  
  
```  
' BeginDeleteProcedureVB  
Sub Main()  
    On Error GoTo DeleteProcedureError  
  
    Dim cat As New ADOX.Catalog  
  
    ' Open the catalog.  
    cat.ActiveConnection = _  
        "Provider='Microsoft.Jet.OLEDB.4.0';" & _  
        "Data Source='Northwind.mdb';"  
  
    ' Delete the procedure.  
    cat.Procedures.Delete "CustomerById"  
  
    'Clean up.  
    Set cat.ActiveConnection = Nothing  
    Set cat = Nothing  
    Exit Sub  
  
DeleteProcedureError:  
    Set cat = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
End Sub  
' EndDeleteProcedureVB  
```  
  
## <a name="see-also"></a>См. также:  
 [Свойство ActiveConnection (ADOX)](./activeconnection-property-adox.md)   
 [Объект каталога (ADOX)](./catalog-object-adox.md)   
 [Метод Delete (ADOX Collections)](./delete-method-adox-collections.md)   
 [Объект процедуры (ADOX)](./procedure-object-adox.md)   
 [Коллекция Procedures (ADOX)](./procedures-collection-adox.md)