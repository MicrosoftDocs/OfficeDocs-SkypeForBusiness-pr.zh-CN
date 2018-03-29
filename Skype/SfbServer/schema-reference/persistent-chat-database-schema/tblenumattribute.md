---
title: tblEnumAttribute
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute 是一个硬编码表包含节点表中使用的可见性和行为特性。
ms.openlocfilehash: 24208b56aba586af500a2f659a2d5cbf1a47234d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute 是一个硬编码表包含节点表中使用的可见性和行为特性。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint，不为空  <br/> |该属性的 ID。  <br/> |
|属性名称  <br/> |nvarchar (256) 不为空  <br/> |该属性的名称。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|attributeID  <br/> |为主键。  <br/> |
   
**表值**

|**attributeID**|**属性名称**|
|:-----|:-----|
|1  <br/> |可见性。  <br/> |
|2  <br/> |行为。  <br/> |
   
## <a name="see-also"></a>另请参阅

#### 

[tblNode](tblnode.md)

