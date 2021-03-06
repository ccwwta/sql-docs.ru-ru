---
description: Метод Find (ADO)
title: Метод Find (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- Recordset15::raw_Find
- Recordset15::Find
helpviewer_keywords:
- Find method [ADO]
ms.assetid: 55c9810a-d8ca-46c2-a9dc-80e7ee7aa188
author: rothja
ms.author: jroth
ms.openlocfilehash: 8335b09bbb7fa044492d1a080b34084be7860a5a
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100033927"
---
# <a name="find-method-ado"></a>Метод Find (ADO)
Выполняет поиск в [наборе записей](./recordset-object-ado.md) для строки, удовлетворяющей заданным критериям. При необходимости можно указать направление поиска, начальную строку и смещение от начальной строки. Если условия соблюдены, текущее расположение строки устанавливается на найденной записи; в противном случае устанавливается значение end (или Start) **набора записей**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Find (Criteria, SkipRows, SearchDirection, Start)  
```  
  
#### <a name="parameters"></a>Параметры  
 *Критерии*  
 **Строковое** значение, содержащее инструкцию, указывающую имя столбца, оператор сравнения и значение, используемые в поиске.  
  
 *скипровс*  
 Необязательный элемент. Значение **типа Long** , значение по умолчанию которого равно нулю, которое указывает смещение строки от текущей строки или *открывающую* закладку для начала поиска. По умолчанию поиск начнется в текущей строке.  
  
 *сеарчдиректион*  
 Необязательный элемент. Значение [сеарчдиректионенум](./searchdirectionenum.md) , указывающее, должен ли поиск начинаться с текущей строки или из следующей доступной строки в направлении поиска. Неудачный поиск останавливается в конце **набора записей** , если значение равно **адсеарчфорвард**. Неудачный поиск останавливается в начале **набора записей** , если значение равно **адсеарчбакквард**.  
  
 *Start*  
 Необязательный элемент. **Вариант** закладки, которая выступает в качестве начальной положения для поиска.  
  
## <a name="remarks"></a>Remarks  
 В *критерии* можно указать только имя из одного столбца. Этот метод не поддерживает поиск по нескольким столбцам.  
  
 Оператор сравнения в *критериях* может иметь значение " **>** " (больше), "* * \<**" (less than), "=" (equal), "> =" (больше или равно), "<=" (меньше или равно), "<>" (не равно) или "Like" (сопоставление шаблонов).  
  
 Значением в поле *критерий* может быть строка, число с плавающей запятой или дата. Строковые значения разделяются одинарными кавычками или символами "#" (знак решетки) (например, "State =" WA "или" State = #WA # "). Значения даты разделяются знаками "#" (знак решетки) (например, "start_date > #7/22/97 #"). Эти значения могут содержать часы, минуты и секунды для указания меток времени, но не должны содержать миллисекунды или ошибки.  
  
 Если оператор сравнения имеет значение LIKE, строковый параметр может содержать звездочку (*) для поиска одного или нескольких вхождений любого символа или подстроки. Например, "состояние Like \* " "соответствует Майн и Массачусетс. Для поиска подстроки, содержащейся в значениях, можно также использовать начальную и конечную звездочки. Например, "состояние Like" \* соответствует " \* Аляска, как Арканзас так и Массачусетс.  
  
 Звездочки можно использовать только в конце строки условий или в начале и в конце строки критерия, как показано выше. Нельзя использовать звездочку в качестве первого подстановочного знака ("* str") или встроенного подстановочного знака ( \* r). Это приведет к ошибке.  
  
> [!NOTE]
>  Если текущая строка строки не задана перед вызовом **Find**, возникнет ошибка. Любой метод, который задает расположение строки, например [MoveFirst](./movefirst-movelast-movenext-and-moveprevious-methods-ado.md), должен вызываться перед вызовом **Find**.  
  
> [!NOTE]
>  Если вызвать метод **Find** для набора записей, а текущее расположение в наборе записей находится в последней записи или конце файла (EOF), ничего не будет найдено. Необходимо вызвать метод **MoveFirst** , чтобы установить текущую позицию или курсор на начало набора записей.  
  
## <a name="applies-to"></a>Применение  
 [Объект Recordset (ADO)](./recordset-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример метода Find (Visual Basic)](./find-method-example-vb.md)   
 [Свойство index](./index-property.md)   
 [Оптимизация Property-Dynamic (ADO)](./optimize-property-dynamic-ado.md)   
 [Метод Seek](./seek-method.md)