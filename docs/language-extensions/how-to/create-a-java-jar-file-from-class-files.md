---
title: Создание JAR-файла Java из файлов класса
description: Упаковывайте файлы класса в JAR-файл при использовании расширений языка SQL Server для выполнения кода Java.
author: dphansen
ms.author: davidph
ms.date: 11/05/2019
ms.topic: how-to
ms.prod: sql
ms.technology: language-extensions
monikerRange: '>=sql-server-ver15||>=sql-server-linux-ver15'
ms.openlocfilehash: d5ae0b8975e47f64f6ecac8a5b8e2977b7dce93f
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100081535"
---
# <a name="create-a-java-jar-file-from-class-files"></a>Создание JAR-файла Java из файлов класса
[!INCLUDE [SQL Server 2019 and later](../../includes/applies-to-version/sqlserver2019.md)]

Сведения о том, как упаковывать файлы класса в JAR-файл при использовании [расширений языка SQL Server](../language-extensions-overview.md) для выполнения кода Java. Рекомендуется упаковывать файлы.

## <a name="create-a-jar-file"></a>Создание JAR-файла

Чтобы создать JAR-файл из файлов класса, перейдите в папку с файлом класса и выполните следующую команду:

```cmd
jar -cf <MyJar.jar> *.class
```

Убедитесь, что путь к `jar.exe` включен в системную переменную PATH. Либо укажите полный путь к этому файлу, который расположен в подпапке `/bin` папки JDK. Пример:

```cmd
C:\Users\MyUser\Desktop\jdk1.8.0_201\bin\jar -cf <MyJar.jar> *.class
```

## <a name="next-steps"></a>Дальнейшие действия

+ [Вызов среды выполнения Java в расширениях языка SQL Server](../how-to/call-java-from-sql.md)