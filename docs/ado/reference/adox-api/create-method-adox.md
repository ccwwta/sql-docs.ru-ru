---
description: Метод Create (ADOX)
title: Метод Create (ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _Catalog::raw_Create
- _Catalog::Create
helpviewer_keywords:
- Create method [ADOX]
ms.assetid: 64f5c21c-b581-42d8-bdc7-c4f1bebaf105
author: rothja
ms.author: jroth
ms.openlocfilehash: b44be7497ca6952dd88d6f18ac0b42a6c989db36
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99172206"
---
# <a name="create-method-adox"></a>Метод Create (ADOX)
Создает новый каталог.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Catalog.Create ConnectString  
```  
  
#### <a name="parameters"></a>Параметры  
 *ConnectString*  
 **Строковое** значение, используемое для подключения к источнику данных.  
  
## <a name="remarks"></a>Замечания  
 Метод **CREATE** создает и открывает новое [соединение](../ado-api/connection-object-ado.md) ADO с источником данных, указанным в *ConnectString*. В случае успеха новый объект **Connection** назначается свойству [ActiveConnection](./activeconnection-property-adox.md) .  
  
 Если поставщик не поддерживает создание новых каталогов, возникнет ошибка.  
  
## <a name="applies-to"></a>Применение  
 [Объект Catalog (ADOX)](./catalog-object-adox.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример метода Create (Visual Basic)](./create-method-example-vb.md)   
 [Свойство ActiveConnection (ADOX)](./activeconnection-property-adox.md)