---
description: Свойство Charset (ADO)
title: Свойство Charset (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _Stream::Charset
helpviewer_keywords:
- Charset property [ADO]
ms.assetid: e42507cb-9b46-4ce4-8191-2948eaf14ca2
author: rothja
ms.author: jroth
ms.openlocfilehash: 3fa8b9b5d657208784cd6e9f78e033ebc84f51b6
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99167786"
---
# <a name="charset-property-ado"></a>Свойство Charset (ADO)
Указывает набор символов, в который содержимое текстового [потока](./stream-object-ado.md) должно быть переведено для хранения во внутреннем буфере объекта **потока** .  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает или возвращает **строковое** значение, указывающее набор символов, в который будет переведено содержимое **потока** . Значение по умолчанию — **Unicode**. Допустимые значения — типичные строки, передаваемые через интерфейс в виде имен наборов символов Интернета (например, "ISO-8859-1", "Windows-1252" и т. д.). Список имен наборов символов, известных системе, см. в подразделах HKEY_CLASSES_ROOT\MIME\Database\Charset в реестре Windows.  
  
## <a name="remarks"></a>Замечания  
 В объекте текстового **потока** текстовые данные хранятся в наборе символов, указанном в свойстве **CharSet** . Значение по умолчанию — Unicode. Свойство **CharSet** используется для преобразования данных, поступающих в **поток** , или из **потока**. Например, если **поток** содержит данные ISO-8859-1 и данные копируются в BSTR, объект **Stream** преобразует данные в Юникод. То же самое будет наблюдаться и в обратной ситуации.  
  
 Для открытого **потока** текущая [позиции](./position-property-ado.md) должна находиться в начале **потока** (0), чтобы иметь возможность установить **CharSet**.  
  
 **CharSet** используется только с объектами текстового **потока** ([Type](./type-property-ado-stream.md) — **адтипетекст**). Это свойство игнорируется, если **Type** имеет значение **адтипебинари**.  
  
 Пример кода см. в разделе [Шаг 4. Заполнение текстового поля сведений](../../guide/data/step-4-populate-the-details-text-box.md).  
  
## <a name="applies-to"></a>Применение  
 [Объект Stream (ADO)](./stream-object-ado.md)