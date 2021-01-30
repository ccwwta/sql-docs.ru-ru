---
description: sys.xml_schema_attributes (Transact-SQL)
title: sys.xml_schema_attributes (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
f1_keywords:
- xml_schema_attributes_TSQL
- xml_schema_attributes
- sys.xml_schema_attributes_TSQL
- sys.xml_schema_attributes
dev_langs:
- TSQL
helpviewer_keywords:
- sys.xml_schema_attributes catalog view
ms.assetid: dd0c98aa-5e72-4df6-96d9-482786c8dbb1
author: WilliamDAssafMSFT
ms.author: wiassaf
ms.openlocfilehash: 135d3d376c79f6ac6ab6c75fbad206777c71b5a5
ms.sourcegitcommit: 33f0f190f962059826e002be165a2bef4f9e350c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99206443"
---
# <a name="sysxml_schema_attributes-transact-sql"></a>sys.xml_schema_attributes (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Возвращает **строку на каждый** компонент схемы XML, являющийся атрибутом, **symbol_space** .  

|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**\<inherited columns>**|--|Наследует от [sys.xml_schema_components](../../relational-databases/system-catalog-views/sys-xml-schema-components-transact-sql.md).|  
|**is_default_fixed**|**bit**|1 = значение по умолчанию зафиксировано. Это значение не может быть заменено в экземпляре XML.<br /><br /> 0 = значение по умолчанию не зафиксировано для атрибута (по умолчанию).|  
|**must_be_qualified**|**bit**|1 = для атрибута должно быть явно указано пространство имен.<br /><br /> 0 = пространство имен для атрибута может быть указано неявно (по умолчанию).|  
|**default_value**|**nvarchar**<br /><br /> **(4000)**|Значение атрибута по умолчанию. Если значение по умолчанию не задано, то значение равно NULL.|  
  
## <a name="permissions"></a>Разрешения  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Дополнительные сведения см. в разделе [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>См. также:  
 [Схемы XML &#40;представления каталога системы типов XML&#41; &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/xml-schemas-xml-type-system-catalog-views-transact-sql.md)   
 [Представления каталога (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
