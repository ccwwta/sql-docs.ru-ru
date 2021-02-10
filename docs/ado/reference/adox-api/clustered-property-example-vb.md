---
description: Пример свойства Clustered (Visual Basic)
title: Пример свойства Clustered (Visual Basic) | Документация Майкрософт
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
- Clustered property [ADOX], Visual Basic example
ms.assetid: 1cd30769-c8af-43e7-be27-12ed0434daa1
author: rothja
ms.author: jroth
ms.openlocfilehash: b721a53830f72fa506dcd6ba53ab6e37f48bedde
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100054399"
---
# <a name="clustered-property-example-vb"></a>Пример свойства Clustered (Visual Basic)
В этом примере демонстрируется свойство [Clustered](./clustered-property-adox.md) [индекса](./index-object-adox.md). Обратите внимание, что базы данных Microsoft Jet не поддерживают кластеризованные индексы, поэтому в этом примере будет возвращено **значение false** для свойства **Clustered** всех индексов в базе данных **Northwind** .  
  
```  
' BeginClusteredVB  
Sub Main()  
    On Error GoTo ClusteredXError  
  
    Dim cnn As New ADODB.Connection  
    Dim cat As New ADOX.Catalog  
    Dim tblLoop As ADOX.Table  
    Dim idxLoop As ADOX.Index  
    Dim strCnn As String  
  
    strCnn = "Provider='SQLOLEDB';Data Source='MySqlServer';Initial Catalog='pubs';" & _  
        "Integrated Security='SSPI';"  
    ' Connect to the catalog.  
    cnn.Open strCnn  
    cat.ActiveConnection = cnn  
  
    ' Enumerate the tables.  
    For Each tblLoop In cat.Tables  
        'Enumerate the indexes.  
        For Each idxLoop In tblLoop.Indexes  
            Debug.Print tblLoop.Name & " " & _  
                idxLoop.Name & " " & idxLoop.Clustered  
        Next idxLoop  
    Next tblLoop  
  
    'Clean up.  
    cnn.Close  
    Set cat = Nothing  
    Set cnn = Nothing  
    Exit Sub  
  
ClusteredXError:  
  
    Set cat = Nothing  
  
    If Not cnn Is Nothing Then  
        If cnn.State = adStateOpen Then cnn.Close  
    End If  
    Set cnn = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
End Sub  
' EndClusteredVB  
```  
  
## <a name="see-also"></a>См. также:  
 [Объект каталога (ADOX)](./catalog-object-adox.md)   
 [Свойство Clustered (ADOX)](./clustered-property-adox.md)   
 [Объект index (ADOX)](./index-object-adox.md)   
 [Объект Table (ADOX)](./table-object-adox.md)