---
description: Создание файлов подключения к серверу (MySQLToSQL)
title: Создание файлов подключения к серверу (MySQLToSQL) | Документация Майкрософт
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Server connection file validation
- Server connection files
ms.assetid: df0e970c-da0b-4118-b359-c9dcbbad16d6
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: 439d70f428fff6e5445fca54e8bd669096a1c6c6
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100016633"
---
# <a name="creating-the-server-connection-files-mysqltosql"></a>Создание файлов подключения к серверу (MySQLToSQL)
Сведения о сервере можно указать либо в разделе Servers файла сценария, либо в отдельном файле соединения сервера. Параметр командной строки для файла соединения сервера имеет значение, `-c <serverconnectionfile>` . Если один и тот же идентификатор сервера имеется как в файле скрипта, так и в файле соединения сервера, то будет считаться определение сервера в файле скрипта.  
  
**Пример**.  
  
```xml  
<!--Sample of server connection file commands -->  
  
<mysql name ="<source-server-unique-name>">  
  
   <standard-mode>  
  
      <server value ="<server-name>"/>  
  
      <user-id value ="<user-name>"/>  
  
      <password value ="<password>"/>  
  
      <port value ="<port>"/>  
  
   </standard-mode>  
  
</mysql>  
```  
  
```xml  
<!--Connection to SQL Server-->  
  
<sql-server name="<target-server-unique-name>">  
  
   <sql-server-authentication>  
  
      <server value="<server-name>"/>  
  
      <database value="<database-name>"/>  
  
      <user-id value="<user-name>"/>  
  
      <password value="<password>"/>  
  
      <encrypt value="<true/false>"/>  
  
      <trust-server-certificate value="<true/false>"/>  
  
   </sql-server-authentication>  
  
</sql-server>  
```  
  
```xml  
<!--Connection to SQL Azure-->  
  
<sql-azure name="<target-server-unique-name>">  
  
   <server value="<server-name>"/>  
  
   <database value="<database-name>"/>  
  
   <user-id value="<user-name>"/>  
  
   <password value="<password>"/>  
  
</sql-azure>  
```  
  
## <a name="server-connection-file-validation"></a>Проверка файлов подключения к серверу  
Пользователь может легко проверить файл подключения своего сервера относительно файла определения схемы **2ssconsolescriptserversschema. xsd** , доступного в папке Schemas.  
  
## <a name="next-step"></a>Следующий шаг  
Следующий шаг в работе консоли заключается [в выполнении консоли SSMA &#40;MySQLToSQL&#41;](../../ssma/mysql/executing-the-ssma-console-mysqltosql.md)  
  
## <a name="see-also"></a>См. также:  
[Исполнение консоли SSMA (MySQL)](./executing-the-ssma-console-mysqltosql.md)  
