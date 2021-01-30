---
description: Примеры методов GetObjectOwner и SetObjectOwner (Visual Basic)
title: Примеры методов примеры методов getobjectowner и SetObjectOwner (Visual Basic) | Документация Майкрософт
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
- SetObjectOwner method [ADOX], Visual Basic example
- GetObjectOwner method [ADOX], Visual Basic example
ms.assetid: e44ec3d4-42ae-447d-aaed-bdea53cb0cca
author: rothja
ms.author: jroth
ms.openlocfilehash: 34e056c23c7192ba1e9d2810df88bb5f0e1a20aa
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99172085"
---
# <a name="getobjectowner-and-setobjectowner-methods-example-vb"></a>Примеры методов GetObjectOwner и SetObjectOwner (Visual Basic)
В этом примере демонстрируются методы [примеры методов getobjectowner](./getobjectowner-method-adox.md) и [SetObjectOwner](./setobjectowner-method.md) . В этом коде предполагается наличие учетной записи группы (см. Дополнительные сведения о добавлении этой группы в систему в разделе [группы и пользователи добавим, метод ChangePassword (VB)](./groups-and-users-append-changepassword-methods-example-vb.md) ). Владелец таблицы Categories имеет значение Accounting.  
  
```  
' BeginOwnersVB  
Sub OwnersX()  
  
    Dim tblLoop As New ADOX.Table  
    Dim cat As New ADOX.Catalog  
    Dim strOwner As String  
  
    ' Open the Catalog.  
    cat.ActiveConnection = "Provider=Microsoft.Jet.OLEDB.4.0;" & _  
        "Data Source=c:\Program Files\" & _  
        "Microsoft Office\Office\Samples\Northwind.mdb;" & _  
        "jet oledb:system database=" & _  
        "c:\Program Files\Microsoft Office\Office\system.mdw"  
  
    ' Print the original owner of Categories  
    strOwner = cat.GetObjectOwner("Categories", adPermObjTable)  
    Debug.Print "Owner of Categories: " & strOwner  
  
    ' Set the owner of Categories to Accounting  
    cat.SetObjectOwner "Categories", adPermObjTable, "Accounting"  
  
    ' List the owners of all tables and columns in the catalog.  
    For Each tblLoop In cat.Tables  
        Debug.Print "Table: " & tblLoop.Name  
        Debug.Print "   Owner: " & _  
            cat.GetObjectOwner(tblLoop.Name, adPermObjTable)  
    Next tblLoop  
  
    ' Restore the original owner of Categories  
    cat.SetObjectOwner "Categories", adPermObjTable, strOwner  
  
End Sub  
' EndOwnersVB  
```  
  
## <a name="see-also"></a>См. также:  
 [Объект каталога (ADOX)](./catalog-object-adox.md)   
 [Метод примеры методов getobjectowner (ADOX)](./getobjectowner-method-adox.md)   
 [Метод SetObjectOwner](./setobjectowner-method.md)