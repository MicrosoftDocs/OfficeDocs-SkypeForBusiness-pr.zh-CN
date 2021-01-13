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
ms.openlocfilehash: a13bfbe79d1eb118f0727f390816a26d35a508d0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816022"
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
|2   <br/> |1   <br/> |private  <br/> |
|3   <br/> |1   <br/> |范围  <br/> |
|4   <br/> |2   <br/> |normal  <br/> |
|5   <br/> |2   <br/> |大会堂  <br/> |
|6   <br/> |1   <br/> |open  <br/> |
   
## <a name="see-also"></a>另请参阅

[tblNode](tblnode.md)
