---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute 是一个硬编码表，包含用于节点表的 Visibility 和 Behavior 属性。
ms.openlocfilehash: 7555656f02fa7808e54100c03de8f80e0e078678
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879697"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute 是一个硬编码表，包含用于节点表的 Visibility 和 Behavior 属性。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint，不为 null  <br/> |属性的 ID。  <br/> |
|属性名称  <br/> |nvarchar (256)，不为 null  <br/> |属性的名称。  <br/> |
   
**关键字**

|**列**|**说明**|
|:-----|:-----|
|attributeID  <br/> |主键。  <br/> |
   
**表值**

|**attributeID**|**属性名称**|
|:-----|:-----|
|1  <br/> |可见性。  <br/> |
|2  <br/> |行为。  <br/> |
   
## <a name="see-also"></a>另请参阅

[tblNode](tblnode.md)
