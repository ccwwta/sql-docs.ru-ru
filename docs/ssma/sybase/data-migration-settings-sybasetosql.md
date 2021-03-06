---
description: Параметры миграции данных (SybaseToSQL)
title: Параметры переноса данных (SybaseToSQL) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 94d7a083-2dbc-4e3d-94dd-92b7ff9d0c2d
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: 6b3598ebd679a85b8965babccfee4fc3658a08b2
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100056609"
---
# <a name="data-migration-settings-sybasetosql"></a>Параметры миграции данных (SybaseToSQL)
  
## <a name="data-migration-settings"></a>Параметры миграции данных  
**Параметры переноса данных** позволяют пользователю создавать пользовательские запросы для переноса данных.  
  
-   Эта вкладка доступна, если для параметра **Параметры расширенной миграции данных** задано значение **Показать** и она скрыта, если параметру задано значение **скрывать** в параметрах проекта. Дополнительные сведения о параметрах миграции проекта см. в разделе [Параметры проекта (миграция)](./project-settings-migration-sybasetosql.md) .  
  
-   Анализ пользовательских инструкций SQL будет реализован на вкладке " **Параметры переноса данных** " узла "Таблица".  
  
-   Ниже перечислены два флажка, доступные в **параметрах переноса данных** визуализациям.:  
  
    1.  Усечение таблицы SQL Server  
  
    2.  Использовать настраиваемый выбор  
  
1.  **Усечение SQL Server таблицы:**  
     Этот параметр позволяет пользователю получить четкое представление о перенесенных данных в целевой базе данных.  
  
    -   По умолчанию это текстовое поле отмечено флажком.  
  
    -   Если это текстовое поле не отмечено, то переносимые данные будут добавлены к существующим данным в целевой базе данных.  
  
2.  **Использовать пользовательское выделение:**  
     Этот параметр позволяет пользователю изменить имеющуюся инструкцию **SELECT** (инструкция **SELECT** позволяет пользователям выбирать данные для отображения в целевой базе данных).  
  
    1.  По умолчанию это текстовое поле не отмечено.  
  
    2.  Если это текстовое поле отмечено, оно позволяет пользователям изменять имеющуюся инструкцию **SELECT** .  
  
Визуализациям есть две кнопки:  
  
-   **Применить:** Нажмите кнопку **Применить** , чтобы применить измененные параметры.  
  
-   **Отмена:** Нажмите кнопку **"Отмена"** , чтобы восстановить параметры до внесения изменений.  
  
## <a name="see-also"></a>См. также:  
[Перенос данных Sybase в SQL Server и SQL Azure](./migrating-sybase-ase-data-into-sql-server-azure-sql-db-sybasetosql.md)  
