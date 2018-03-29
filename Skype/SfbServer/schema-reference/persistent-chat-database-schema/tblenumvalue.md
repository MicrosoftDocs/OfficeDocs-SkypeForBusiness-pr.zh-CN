---
title: tblEnumValue
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue 是一个包含节点表中使用的属性的可见性和行为的值的硬编码表。
ms.openlocfilehash: 4957f87401dc93cc98d18fa5b1844e13daaefabd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue 是一个包含节点表中使用的属性的可见性和行为的值的硬编码表。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint，不为空  <br/> |ID 的值。  <br/> |
|attributeID  <br/> |smallint，不为空  <br/> |该属性的 ID。  <br/> |
|attributeValue  <br/> |nvarchar (256) 不为空  <br/> |值的名称。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|valueID  <br/> |为主键。  <br/> |
|attributeID  <br/> |TblEnumAttribute.attributeID 表中查找与外键。  <br/> |
   
**表值**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |专用  <br/> |
|3  <br/> |1  <br/> |作用域  <br/> |
|4  <br/> |2  <br/> |正常  <br/> |
|5  <br/> |2  <br/> |大会堂  <br/> |
|6  <br/> |1  <br/> |打开  <br/> |
   
## <a name="see-also"></a>另请参阅

#### 

[tblNode](tblnode.md)

