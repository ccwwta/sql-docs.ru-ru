---
description: Настройка шифрования столбцов на месте с помощью Always Encrypted с безопасными анклавами
title: Настройка шифрования столбцов на месте с помощью Always Encrypted с безопасными анклавами | Документация Майкрософт
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
ms.openlocfilehash: 67b74e36ff5b2872e619a4b26fabdd05428e6a16
ms.sourcegitcommit: 8ca4b1398e090337ded64840bcb8d6c92d65c29e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2021
ms.locfileid: "98534843"
---
# <a name="configure-column-encryption-in-place-using-always-encrypted-with-secure-enclaves"></a>Настройка шифрования столбцов на месте с помощью Always Encrypted с безопасными анклавами 
[!INCLUDE [sqlserver2019-windows-only-asdb](../../../includes/applies-to-version/sqlserver2019-windows-only-asdb.md)]

[Always Encrypted с безопасными анклавами](always-encrypted-enclaves.md) поддерживает криптографические операции в столбцах базы данных на месте — внутри безопасного анклава в [!INCLUDE[ssde-md](../../../includes/ssde-md.md)]. Шифрование на месте устраняет необходимость перемещения данных для таких операций за пределы базы данных, что делает криптографические операции более быстрыми и надежными. 

> [!NOTE]
> Несмотря на преимущества шифрования на месте в плане производительности, криптографические операции в больших таблицах могут занимать много времени и потреблять значительные ресурсы и потенциально влиять на производительность и доступность приложений.

Шифрование на месте позволяет также активировать операции шифрования с помощью инструкции [ALTER TABLE ALTER COLUMN (Transact-SQL)](../../../t-sql/statements/alter-table-transact-sql.md), что невозможно без анклава.

## <a name="prerequisites"></a>Предварительные требования
Ниже приведены поддерживаемые криптографические операции и требования для ключей шифрования столбцов, используемых для этих операций.
- Шифрование столбца с открытым текстом. Ключ шифрования столбца, используемый для шифрования столбца, должен поддерживать анклав.
- Повторное шифрование зашифрованного столбца с помощью нового типа шифрования или (и) нового ключа шифрования столбца. Ключ шифрования текущего столбца и новый ключ шифрования столбца (если он отличается от текущего) оба должны поддерживать анклав.
- Расшифровка зашифрованного столбца. Ключ шифрования столбца, защищающий столбец, должен поддерживать анклав.

Сведения о том, как проверить, что ключи шифрования столбцов поддерживают анклав, см. в разделе [Управление ключами для Always Encrypted с безопасными анклавами](always-encrypted-enclaves-manage-keys.md).

Кроме того, необходимо убедиться, что среда соответствует общим [требованиям для выполнения инструкций, использующих безопасные анклавы](always-encrypted-enclaves-query-columns.md#prerequisites-for-running-statements-using-secure-enclaves).

Пользователь или приложение, запускающее криптографические операции, должны иметь разрешения на внесение изменений схемы в таблицу, содержащую затрагиваемые столбцы, и на доступ к главным ключам столбцов, используемым в операции, и к соответствующим метаданным ключа в базе данных.

Шифрование на месте можно активировать только с помощью инструкции [ALTER TABLE ALTER COLUMN (Transact-SQL)](../../../t-sql/statements/alter-table-transact-sql.md) из среды SQL Server Management Studio или другого пользовательского приложения. См. [Настройка шифрования столбцов на месте с помощью Transact-SQL](always-encrypted-enclaves-configure-encryption-tsql.md).

> [!NOTE]
> В настоящее время мастер [Always Encrypted](always-encrypted-wizard.md) и командлет [Set-SqlColumnEncryption](/powershell/module/sqlserver/set-sqlcolumnencryption) не поддерживают шифрование на месте и всегда загружают данные для криптографических операций, даже если ваша конфигурация соответствует приведенным выше требованиям. 

## <a name="next-steps"></a>Next Steps
- [Настройка шифрования столбцов на месте с помощью Transact-SQL](always-encrypted-enclaves-configure-encryption-tsql.md)
- [Создание и использование индексов в столбце с помощью Always Encrypted с безопасными анклавами](always-encrypted-enclaves-create-use-indexes.md)
- [Разработка приложений с помощью Always Encrypted с безопасными анклавами](always-encrypted-enclaves-client-development.md)

## <a name="see-also"></a>См. также:  
- [Устранение распространенных неполадок Always Encrypted с безопасными анклавами](always-encrypted-enclaves-troubleshooting.md)