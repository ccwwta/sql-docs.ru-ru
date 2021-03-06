---
description: Подключение к SQL Server (Акцесстоскл)
title: Подключение к SQL Server (Акцесстоскл) | Документация Майкрософт
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: ceb77a97-d6d5-4a92-90a6-342e97d12b54
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: f2c98dedcb785f7425bde3f3186aec278bb762d4
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100076285"
---
# <a name="connect-to-sql-server-accesstosql"></a>Подключение к SQL Server (Акцесстоскл)
Используйте диалоговое окно **Подключение к SQL Server** , чтобы подключиться к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , на который требуется выполнить миграцию. Чтобы открыть диалоговое окно **Подключение к SQL Server** , в меню **файл** выберите пункт **подключиться к SQL Server**.  
  
## <a name="options"></a>Параметры  
**Имя сервера**  
Введите или выберите экземпляр SQL Server для подключения. По умолчанию отображается экземпляр, который был подключен к последнему.  
  
-   При подключении к экземпляру по умолчанию на локальном компьютере можно ввести либо **localhost** , либо точку (**.**).  
  
-   При подключении к экземпляру по умолчанию на другом компьютере введите имя компьютера.  
  
-   При подключении к именованному экземпляру на другом компьютере введите имя компьютера, обратную косую черту и имя экземпляра, например *MyServer* \\ *myInstance*.  
  
**Порт сервера**  
Если экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не настроен для приема подключений через порт по умолчанию (1433), введите номер порта. В противном случае оставьте это значение пустым.  
  
**База данных**  
Укажите базу данных для переноса объектов и данных. Этот параметр недоступен при повторном подключении к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
**Аутентификация**  
Выберите метод проверки подлинности, используемый для подключения к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Чтобы использовать текущую учетную запись Windows, выберите Проверка подлинности Windows. Чтобы указать [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имя входа и пароль, выберите [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Проверка подлинности.  
  
**Имя пользователя**  
Если используется [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Проверка подлинности, введите имя входа для этого экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Если используется проверка подлинности Windows, этот параметр недоступен.  
  
**Пароль**  
Если используется [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Проверка подлинности, введите пароль для имени входа на этом экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Если используется проверка подлинности Windows, этот параметр недоступен.  
  
**Шифровать соединение**  
Если вы хотите безопасно подключаться к SQL Server, используйте шифрование соединения, установив флажок **шифровать подключение** .  
  
**Надежный сертификат сервера**  
Если вы хотите использовать этот параметр, установите флажок **доверять сертификату сервера** .  
  
> [!NOTE]  
> Чтобы включить **доверенный сертификат сервера**, параметру "Encrypt" необходимо присвоить значение **true**.  
  
