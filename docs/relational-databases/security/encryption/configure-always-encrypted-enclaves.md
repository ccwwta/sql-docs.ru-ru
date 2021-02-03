---
title: Настройка и использование Always Encrypted с безопасными анклавами | Документация Майкрософт
description: Сведения о настройке и использовании Always Encrypted с безопасными анклавами SQL Server и Базой данных SQL Azure, что делает возможным использование расширенных функций с конфиденциальными данными.
ms.custom: ''
ms.date: 01/15/2021
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: vanto
ms.technology: security
ms.topic: conceptual
author: jaszymas
ms.author: jaszymas
monikerRange: '>= sql-server-ver15'
ms.openlocfilehash: 73a1c9f3a39ce51ce6ecc347af2e2eb0fb173fb6
ms.sourcegitcommit: b1cec968b919cfd6f4a438024bfdad00cf8e7080
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2021
ms.locfileid: "99237303"
---
# <a name="configure-and-use-always-encrypted-with-secure-enclaves"></a>Настройка и использование Always Encrypted с безопасными анклавами 

[!INCLUDE [sqlserver2019-windows-only-asdb](../../../includes/applies-to-version/sqlserver2019-windows-only-asdb.md)]

[Always Encrypted с безопасными анклавами](always-encrypted-enclaves.md) расширяет существующую функцию [Always Encrypted](always-encrypted-database-engine.md), чтобы обеспечить расширенные функции защиты конфиденциальных данных. В этой статье перечислены распространенные задачи по настройке и использованию этой функции.

См. руководства о том, как приступить к работе с Always Encrypted с безопасными анклавами:

- [Учебник. Начало работы с Always Encrypted и безопасными анклавами в SQL Server](../tutorial-getting-started-with-always-encrypted-enclaves.md)
- [Учебник. Начало работы с Always Encrypted и безопасными анклавами в Базе данных SQL Azure](/azure/azure-sql/database/always-encrypted-enclaves-getting-started)

## <a name="set-up-the-secure-enclave-and-attestation"></a>Настройка безопасного анклава и аттестации

Прежде чем использовать Always Encrypted с безопасными анклавами, необходимо настроить среду, которая обеспечит доступность безопасного анклава для базы данных. Кроме того, необходимо настроить [аттестацию анклава](always-encrypted-enclaves.md#secure-enclave-attestation). 

Процесс настройки среды зависит от того, используете вы [!INCLUDE[sql-server-2019](../../../includes/sssql19-md.md)] или [!INCLUDE[ssSDSfull](../../../includes/sssdsfull-md.md)].

### <a name="set-up-the-secure-enclave-and-attestation-in-ssnoversion-md"></a>Настройка безопасного анклава и аттестации в [!INCLUDE [ssnoversion-md](../../../includes/ssnoversion-md.md)]

Подробности см. в следующих статьях:
- [Планирование аттестации службы защиты узла](./always-encrypted-enclaves-host-guardian-service-plan.md)
- [Развертывание службы защиты узла для [!INCLUDE [ssnoversion-md](../../../includes/ssnoversion-md.md)]](./always-encrypted-enclaves-host-guardian-service-deploy.md)
- [Регистрация компьютера в службе защиты узла](./always-encrypted-enclaves-host-guardian-service-register.md)
- [Настройка безопасного анклава в SQL Server](always-encrypted-enclaves-configure-enclave-type.md)

### <a name="set-up-the-secure-enclave-and-attestation-in-sssdsfull"></a>Настройка безопасного анклава и аттестации в [!INCLUDE[ssSDSfull](../../../includes/sssdsfull-md.md)]

Подробности см. в следующих статьях:
- [Планирование использования анклавов Intel SGX и аттестация в [!INCLUDE[ssSDSfull](../../../includes/sssdsfull-md.md)]](/azure/azure-sql/database/always-encrypted-enclaves-plan)
- [Включение Intel SGX для Базы данных SQL Azure](/azure/azure-sql/database/always-encrypted-enclaves-enable-sgx)
- [Настройка Аттестации Azure для логического сервера Базы данных SQL Azure](/azure/azure-sql/database/always-encrypted-enclaves-configure-attestation)

## <a name="manage-keys-for-always-encrypted-with-secure-enclaves"></a>Управление ключами для Always Encrypted с безопасными анклавами
Подробные сведения см. в следующих разделах:
- [Управление ключами для Always Encrypted с безопасными анклавами — обзор](always-encrypted-enclaves-manage-keys.md)
- [Подготовка ключей с поддержкой анклава](always-encrypted-enclaves-provision-keys.md)
- [Смена ключей с поддержкой анклава](always-encrypted-enclaves-rotate-keys.md)

## <a name="configure-columns-with-always-encrypted-with-secure-enclaves"></a>Настройка столбцов с помощью Always Encrypted с безопасными анклавами
Подробные сведения см. в следующих разделах:
- [Настройка шифрования столбцов на месте с помощью Always Encrypted с безопасными анклавами — обзор](always-encrypted-enclaves-configure-encryption.md)
- [Настройка шифрования столбцов на месте с помощью Transact-SQL](always-encrypted-enclaves-configure-encryption-tsql.md)
- [Включение Always Encrypted с безопасными анклавами для существующих зашифрованных столбцов](always-encrypted-enclaves-enable-for-encrypted-columns.md)

## <a name="run-transact-sql-statements-using-secure-enclaves"></a>Выполнение инструкций Transact-SQL с помощью безопасных анклавов
Подробные сведения см. в следующих разделах:
- [Выполнение инструкций Transact-SQL с помощью безопасных анклавов](always-encrypted-enclaves-query-columns.md)
- [Устранение распространенных неполадок Always Encrypted с безопасными анклавами](always-encrypted-enclaves-troubleshooting.md)

## <a name="create-and-use-indexes-on-enclave-enabled-columns"></a>Создание и использование индексов в столбцах с поддержкой анклава
Подробные сведения см. в следующих разделах:
- [Создание и использование индексов в столбцах с помощью Always Encrypted с безопасными анклавами](always-encrypted-enclaves-create-use-indexes.md)
  
## <a name="develop-applications-using-always-encrypted-with-secure-enclaves"></a>Разработка приложений с помощью Always Encrypted с безопасными анклавами
Подробные сведения см. в следующих разделах:
- [Разработка приложений с помощью Always Encrypted с безопасными анклавами](always-encrypted-enclaves-client-development.md)
