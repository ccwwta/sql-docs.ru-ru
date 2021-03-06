---
description: Подключение к DB2 (DB2ToSQL)
title: Подключение к DB2 (DB2ToSQL) | Документация Майкрософт
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 9d485fd0-ab5d-402a-a59a-e9982a61b7de
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: 24ffef4775339baf182b01062f2a06136a04abf1
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100081575"
---
# <a name="connect-to-db2-db2tosql"></a>Подключение к DB2 (DB2ToSQL)
Используйте диалоговое окно **Подключение к DB2** для подключения к базе данных DB2, которую требуется перенести.  
  
Чтобы открыть это диалоговое окно, в меню **файл** выберите **подключиться к DB2**. Если подключение было выполнено ранее, команда **повторно подключится к DB2**.  
  
## <a name="options"></a>Параметры  
**Поставщик**  
Выберите поставщик доступа к данным для подключения к базе данных DB2. Доступные поставщики — поставщик клиента DB2 и поставщик OLE DB. Значение по умолчанию — поставщик клиента DB2.  
  
**Режим**  
Выберите стандартный, ТНСНАМЕ или режим строки подключения.  
  
-   В стандартном режиме вводятся или выбираются значения для поставщика, имени сервера, порта сервера, идентификатора безопасности DB2, имени пользователя и пароля.  
  
-   В режиме ТНСНАМЕ введите идентификатор подключения (псевдоним TNS) базы данных DB2, имя пользователя и пароль.  
  
-   В режиме строки подключения вы предоставляете строку подключения.  
  
    > [!IMPORTANT]  
    > Не рекомендуется использовать режим строки подключения, так как текст может содержать пароли и отправляется в виде открытого текста.  
  
По умолчанию используется стандартный режим.  
  
**Имя сервера**  
Введите имя сервера DB2. Имя сервера по умолчанию совпадает с именем компьютера. Это Стандартный режим.  
  
**Порт сервера**  
Если для соединения с DB2 используется номер порта, отличный от 1521 (по умолчанию), введите номер порта. Это Стандартный режим.  
  
**Идентификатор подключения**  
Введите идентификатор подключения DB2. Это псевдоним базы данных, определенный в локальном файле tnsnames. ORA.  
  
Это параметр режима ТНСНАМЕ.  
  
**ИДЕНТИФИКАТОР БЕЗОПАСНОСТИ DB2**  
Введите идентификатор безопасности для базы данных. SID — это идентификатор, который различает базу данных DB2 на компьютере. Идентификатор безопасности по умолчанию для базы данных — первые восемь символов имени базы данных.  
  
Это Стандартный режим.  
  
**Имя пользователя**  
Введите имя пользователя, которое SSMA будет использовать для подключения к базе данных DB2.  
  
**Пароль**  
Введите пароль для имени пользователя.  
  
**Строка соединения**  
> [!IMPORTANT]  
> Не рекомендуется использовать режим строки подключения, так как текст может содержать пароли и отправляется в виде открытого текста.  
  
Если используется режим строки подключения, введите полную строку соединения для соединения с DB2.  
  
Строки подключения состоят из пар имя параметра и значение.  
  
-   Сведения о строках подключения OLE DB см. в [поставщик OLE DB для DB2 (Майкрософт)](../../ado/guide/appendixes/microsoft-ole-db-provider-for-oracle.md) статье библиотеки MSDN.  
  
Для строк подключения SSMA всегда включайте параметр provider. Кроме того, убедитесь, что вы включили параметр Port при подключении к DB2.  
