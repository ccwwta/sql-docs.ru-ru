---
title: Установка SSMA для клиента Oracle (OracleToSQL) | Документация Майкрософт
description: Дополнительные сведения о предварительных требованиях для установки Помощник по миграции SQL Server (SSMA) для клиента Oracle и о том, как установить.
ms.prod: sql
ms.custom: ''
ms.date: 07/14/2020
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: d5d4903d-e296-4bbf-8780-63674c4d62d5
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: 5bed1589c0852acc2d782028f6b9cc253301babe
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100073498"
---
# <a name="installing-ssma-for-oracle-client-oracletosql"></a>Установка SSMA для клиента Oracle (OracleToSQL)

Клиент SSMA состоит из программных файлов, которые выполняют следующие задачи:  
  
- Соединение с базой данных Oracle
- Подключение к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].
- Преобразование объектов базы данных Oracle в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] синтаксис.
- Загрузите объекты в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .
- Перенос данных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .

В этом разделе приведены предварительные требования для установки и инструкции по установке SSMA.

## <a name="prerequisites"></a>Предварительные требования

SSMA предназначен для работы с Oracle 9 или более поздними версиями и всеми выпусками [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .

Перед установкой SSMA убедитесь, что компьютер соответствует следующим требованиям.

- Windows 7 или более поздней версии или Windows Server 2008 или более поздней версии.
- Установщик [!INCLUDE[msCoName](../../includes/msconame_md.md)] Windows версии 3.1 или более поздняя версия.
- [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort_md.md)] Версия 4.7.2 или более поздняя. Его можно получить в [центре разработчиков платформа .NET Framework](https://go.microsoft.com/fwlink/?LinkId=48882).
- Подключение к базам данных Oracle, которые необходимо перенести.
- Доступ к и достаточным разрешениям на компьютере, на котором размещен целевой экземпляр, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или на [!INCLUDE[ssAzure](../../includes/ssazure_md.md)] котором будут перенесены объекты и данные базы данных. Дополнительные сведения см. [в разделе Подключение к SQL Server &#40;OracleToSQL&#41;](../../ssma/oracle/connecting-to-sql-server-oracletosql.md).
- рекомендуется 4 ГБ ОЗУ.  
  
## <a name="installing-the-ssma-for-oracle-client"></a>Установка клиента SSMA для Oracle

SSMA можно загрузить из Интернета. Чтобы скачать последнюю версию, см. [страницу загрузки помощник по миграции SQL Server](https://aka.ms/ssmafororacle).

Чтобы установить клиент SSMA, выполните следующие действия.

1. Дважды щелкните **SSMAforOracle_ *n*. msi**, где *n* — номер сборки.
2. На странице Приветствие нажмите кнопку **Далее**.

   Если предварительные условия не установлены, появится сообщение о том, что необходимо сначала установить необходимые компоненты. Убедитесь, что установлены все необходимые компоненты, а затем снова запустите программу установки.  

3. Прочтите лицензионное соглашение End-User. Если вы согласны, установите флажок **я принимаю условия соглашения**, а затем нажмите кнопку **Далее**.
4. На странице **Выбор типа установки** выберите вариант **Обычная**.
5. На странице **все готово для установки** можно включить или отключить данные телеметрии и автоматические проверки обновлений при каждом запуске средства. Нажмите кнопку **Установить**, чтобы начать установку.

> [!IMPORTANT]
> Удалите все предыдущие версии SSMA для Oracle перед установкой новой версии.

Расположение установки по умолчанию — `C:\Program Files\Microsoft SQL Server Migration Assistant for Oracle`.

Помимо файлов программы SSMA, необходимо также установить пакет SSMA для пакета расширения Oracle на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Дополнительные сведения см. [в разделе Installing SSMA Components on SQL Server](../../ssma/oracle/installing-ssma-components-on-sql-server-oracletosql.md).

## <a name="see-also"></a>См. также раздел

- [Установка компонентов SSMA на SQL Server](../../ssma/oracle/installing-ssma-components-on-sql-server-oracletosql.md)
- [Миграция баз данных Oracle в SQL Server](../../ssma/oracle/migrating-oracle-databases-to-sql-server-oracletosql.md)
