---
author: MikeRayMSFT
ms.prod: sql
ms.technology: big-data-cluster
ms.topic: include
ms.date: 06/22/2020
ms.author: mikeray
ms.openlocfilehash: 599b4072c5d03c8a4753c7c00bc7edc14e0f3b05
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100038953"
---
Начиная с SQL Server 2019 CU5, при развертывании нового кластера с обычной проверкой подлинности все конечные точки, включая шлюз, используют `AZDATA_USERNAME` и `AZDATA_PASSWORD`. Конечные точки в кластерах, обновленных до CU5, продолжают использовать `root` в качестве имени пользователя для подключения к конечной точке шлюза. Это изменение не применяется к развертываниям, в которых используется проверка подлинности с помощью Active Directory. Подробные сведения см. в заметках о выпуске в разделе [Учетные данные для доступа к службам через конечную точку шлюза](../big-data-cluster/release-notes-big-data-cluster.md#credentials-for-accessing-services-through-gateway-endpoint).