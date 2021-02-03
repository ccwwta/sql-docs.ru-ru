---
title: Настройка безопасного анклава в SQL Server
description: Настройка безопасного анклава для Always Encrypted с безопасными анклавами для SQL Server.
ms.custom: ''
ms.date: 01/15/2021
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: vanto
ms.technology: security
ms.topic: conceptual
author: jaszymas
ms.author: jaszymas
monikerRange: '>= sql-server-ver15 || = sqlallproducts-allversions'
ms.openlocfilehash: e6e6dfd3092f4602f652af81e547b63fc1ddc3df
ms.sourcegitcommit: b1cec968b919cfd6f4a438024bfdad00cf8e7080
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2021
ms.locfileid: "99236092"
---
# <a name="configure-the-secure-enclave-in-sql-server"></a>Настройка безопасного анклава в SQL Server

[!INCLUDE [sqlserver2019-windows-only](../../../includes/applies-to-version/sqlserver2019-windows-only.md)]

Прежде чем использовать [Always Encrypted с безопасными анклавами](always-encrypted-enclaves.md) в SQL Server, необходимо настроить экземпляр для инициализации безопасного анклава во время запуска. По умолчанию SQL Server не инициализирует безопасный анклав. Это поведение можно изменить, задав для параметра конфигурации **Тип анклава шифрования столбцов** значение, представляющее допустимый тип анклава для имеющейся среды.

> [!NOTE]
> Ответственным за настройку безопасного анклава является администратор баз данных. См. раздел о [ролях и обязанностях при настройке аттестации с помощью HGS](always-encrypted-enclaves-host-guardian-service-plan.md#roles-and-responsibilities-when-configuring-attestation-with-hgs).

Поддерживаемым типом безопасного анклава для [!INCLUDE[sql-server-2019](../../../includes/sssql19-md.md)] является безопасность на основе виртуализации (VBS). Перед настройкой типа анклава VBS рекомендуется настроить аттестацию с помощью службы защиты узла (HGS) на компьютере, где размещается экземпляр. Сведения о начале работы с HGS см. в статье [Планирование аттестации службы защиты узла](always-encrypted-enclaves-host-guardian-service-plan.md). При настройке аттестации также включается функция безопасности на основе виртуализации, которая необходима для правильной инициализации анклава VBS. Дополнительные сведения см. в разделе [Проверка выполнения функции безопасности на основе виртуализации](always-encrypted-enclaves-host-guardian-service-register.md#step-2-verify-virtualization-based-security-is-running).

Подробные инструкции о настройке типа анклава см. в статье [Настройка типа анклава для параметра конфигурации сервера Always Encrypted](../../../database-engine/configure-windows/configure-column-encryption-enclave-type.md).

## <a name="next-steps"></a>Next Steps

 [Управление ключами для Always Encrypted с безопасными анклавами](always-encrypted-enclaves-manage-keys.md)

## <a name="see-also"></a>См. также:  
 
 [Параметры конфигурации сервера (SQL Server)](../../../database-engine/configure-windows/server-configuration-options-sql-server.md)
