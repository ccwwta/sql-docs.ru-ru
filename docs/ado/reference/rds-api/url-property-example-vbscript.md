---
description: Пример свойства URL (VBScript)
title: Пример свойства URL (VBScript) | Документация Майкрософт
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.prod: sql
ms.prod_service: connectivity
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- URL property [ADO], VBScript example
ms.assetid: 6ae5ac50-c88c-4262-b7ab-f2b3de382a0b
author: rothja
ms.author: jroth
ms.openlocfilehash: f295fd69f61e6359b257f053ac3775223a70603d
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99168720"
---
# <a name="url-property-example-vbscript"></a>Пример свойства URL (VBScript)
> [!IMPORTANT]
>  Начиная с Windows 8 и Windows Server 2012, компоненты RDS больше не включены в операционную систему Windows (Дополнительные сведения см. в статье о совместимости Windows 8 и [Windows server 2012 Cookbook](https://www.microsoft.com/download/details.aspx?id=27416) ). Клиентские компоненты RDS будут удалены в следующей версии Windows. Избегайте использования этого компонента в новых разработках и запланируйте изменение существующих приложений, в которых он применяется. Приложения, использующие RDS, должны переноситься в [службу данных WCF](/dotnet/framework/wcf/).  
  
 В следующем коде показано, как задать свойство **URL** на стороне клиента, чтобы указать ASP-файл, который, в свою очередь, обрабатывает отправку изменений в источник данных.  
  
```  
<!-- BeginURLClientVBS -->  
<%@ Language=VBScript %>  
<html>  
<head>  
    <meta name="VI60_DefaultClientScript"  content=VBScript>  
    <meta name="GENERATOR" content="Microsoft Visual Studio 6.0">  
    <title>URL Property Example (VBScript)</title>  
<style>  
<!--  
body {  
   font-family: 'Verdana','Arial','Helvetica',sans-serif;  
   BACKGROUND-COLOR:white;  
   COLOR:black;  
    }  
.thead {  
   background-color: #008080;   
   font-family: 'Verdana','Arial','Helvetica',sans-serif;   
   font-size: x-small;  
   color: white;  
   }  
.thead2 {  
   background-color: #800000;   
   font-family: 'Verdana','Arial','Helvetica',sans-serif;   
   font-size: x-small;  
   color: white;  
   }  
.tbody {   
   text-align: center;  
   background-color: #f7efde;  
   font-family: 'Verdana','Arial','Helvetica',sans-serif;   
   font-size: x-small;  
    }  
-->  
</style>  
</head>  
  
<body onload=Getdata()>  
<h1>URL Property Example (VBScript)</h1>  
<OBJECT classid=clsid:BD96C556-65A3-11D0-983A-00C04FC29E33 height=1 id=ADC width=1>  
</OBJECT>  
  
<table datasrc="#ADC" align="center">  
<thead>  
<tr id="ColHeaders" class="thead2">  
   <th>FirstName</th>  
   <th>LastName</th>  
   <th>Extension</th>  
</tr>  
</thead>  
<tbody class="tbody">  
<tr>  
   <td><input datafld="FirstName" size=15> </td>  
   <td><input datafld="LastName" size=25> </td>  
   <td><input datafld="Extension" size=15> </td>  
</tr>  
</tbody>  
</table>  
  
<script Language="VBScript">  
Sub Getdata()  
  
      ADC.URL = "https://MyServer/URLServerVBS.asp"  
      ADC.Refresh  
End Sub  
  
</script>  
  
</body>  
</html>  
<!-- EndURLClientVBS -->  
```  
  
 Код на стороне сервера, существующий в **урлсервервбс. ASP** , отправляет обновленный **набор записей** в источник данных.  
  
```  
<!-- BeginURLServerVBS -->  
<%@ Language=VBScript %>  
<%  
  
        ' XML output req's  
    Response.ContentType = "text/xml"  
    const adPersistXML  = 1  
  
        ' recordset vars  
    Dim strSQL, rsEmployees   
    Dim strCnxn, Cnxn  
  
    strCnxn = "Provider='sqloledb';Data Source=" & _  
            Request.ServerVariables("SERVER_NAME") & ";" & _  
            "Integrated Security='SSPI';Initial Catalog='Northwind';"  
    Set Cnxn = Server.CreateObject("ADODB.Connection")  
    Set rsEmployees = Server.CreateObject("ADODB.Recordset")  
  
    strSQL = "SELECT FirstName, LastName, Extension FROM Employees"  
  
    Cnxn.Open strCnxn  
    rsEmployees.Open strSQL, Cnxn  
  
        ' output as XML  
    rsEmployees.Save Response, adPersistXML  
  
        ' Clean up  
    rsEmployees.Close  
    Cnxn.Close  
    Set rsEmployees = Nothing  
    Set Cnxn = Nothing  
%>  
<!-- EndURLServerVBS -->  
```  
  
## <a name="see-also"></a>См. также:  
 [Свойство URL (служба удаленных рабочих столов)](./url-property-rds.md)