---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue 表是一个硬编码表，包含节点表使用的属性的“可见性”值和“行为”值。
ms.openlocfilehash: 732fe5f32a9a92fd3e17098382102433d4c8fa135dbf97cedbf8b3e3e0074b84
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54346348"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue 表是一个硬编码表，包含节点表使用的属性的“可见性”值和“行为”值。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint，不为 null  <br/> |值的 ID。  <br/> |
|attributeID  <br/> |smallint，不为 null  <br/> |属性的 ID。  <br/> |
|attributeValue  <br/> |nvarchar  (256)，不为 null  <br/> |值名称。  <br/> |
   
**Keys**

|**列**|**说明**|
|:-----|:-----|
|valueID  <br/> |主键。  <br/> |
|attributeID  <br/> |其查找包含在 tblEnumAttribute.attributeID 表中的外键。  <br/> |
   
**表值**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |private  <br/> |
|3  <br/> |1  <br/> |范围  <br/> |
|4   <br/> |2  <br/> |normal  <br/> |
|5   <br/> |2  <br/> |auditorium  <br/> |
|6   <br/> |1  <br/> |open  <br/> |
   
## <a name="see-also"></a>另请参阅

[tblNode](tblnode.md)
