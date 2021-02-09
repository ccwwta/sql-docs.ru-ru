---
title: Заметки о выпуске для mssql-tools в Linux и macOS
description: Новые возможности и изменения в выпущенных версиях Microsoft SQL Server Tools.
ms.custom: ''
ms.date: 01/29/2021
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: v-daenge
ms.technology: connectivity
ms.topic: conceptual
author: v-zhangw
ms.author: v-zhangw
manager: kenvh
ms.openlocfilehash: 75f1144e84792b3c9361dcab74dcdbcb7b072268
ms.sourcegitcommit: f30b5f61c514437ea58acc5769359c33255b85b5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2021
ms.locfileid: "99075926"
---
# <a name="release-notes-for-the-microsoft-sql-server-tools-on-linux-and-macos"></a>Заметки о выпуске для инструментов Microsoft SQL Server в Linux и macOS

[!INCLUDE[Driver_ODBC_Download](../../../includes/driver_odbc_download.md)]

В этой статье описываются новые возможности в версиях [!INCLUDE[msCoName](../../../includes/msconame_md.md)] SQL Server Tools на платформах Linux и macOS.

## <a name="17711-january-2021"></a>17.7.1.1 — январь 2021 г.

| Добавленная возможность | Сведения |
| :------------ | :------ |
| Исправление ошибки Sqlcmd | Исправлена ошибка перенаправления ввода и ошибка, из-за которой пустые строки приводили к повторному выполнению. |
| Исправление ошибки Sqlcmd | Исправлены ложные сообщения об ошибках для параметров r, p, X и k при определенном форматировании. |
| Параметр Sqlcmd -z/-Z "Пароль" | Теперь поддерживается. |
| &nbsp; | &nbsp; |

## <a name="17611-july-2020"></a>17.6.1.1, июль 2020 г.

| Добавленная возможность | Сведения |
| :------------ | :------ |
| Обновлено средство синтаксического анализа командной строки sqlcmd | Исправлены ошибки, вызванные непредвиденным поведением при использовании определенных параметров в разном порядке. |
| Обновлены сообщения об ошибках sqlcmd | Исправлены различные несоответствия при возврате ошибок в sqlcmd. |
| Исправлен параметр sqlcmd -Y | Исправлена проблема, когда параметр -Y был неэффективен |
| Исправлено усечение имени столбца sqlcmd | Исправлена проблема неправильного усечения имен столбцов. |
| Коды вывода sqlcmd в Linux | Исправлена проблема, когда отсутствовал код завершения процесса в Linux |
| &nbsp; | &nbsp; |

## <a name="next-steps"></a>Дальнейшие шаги

Дополнительные сведения о подключении с помощью [BCP](connecting-with-bcp.md) и [SQLCMD](connecting-with-sqlcmd.md)!
