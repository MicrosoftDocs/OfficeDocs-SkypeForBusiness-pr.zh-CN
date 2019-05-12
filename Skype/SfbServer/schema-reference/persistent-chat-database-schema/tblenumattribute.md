---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute 是一个硬编码表，包含用于节点表的 Visibility 和 Behavior 属性。
ms.openlocfilehash: b81e8ae09561220df381290eed212ef752820edd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929950"
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
