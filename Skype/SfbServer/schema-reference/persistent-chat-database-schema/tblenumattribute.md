---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute 是一个硬编码表，包含用于节点表的 Visibility 和 Behavior 属性。
ms.openlocfilehash: 7e96b953cd7d53756dd184ae9b0e9190e9a529e0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763260"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute 是一个硬编码表，包含用于节点表的 Visibility 和 Behavior 属性。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint，不为 null  <br/> |属性的 ID。  <br/> |
|attributeName  <br/> |nvarchar (256)，不为 null  <br/> |属性的名称。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|attributeID  <br/> |主键。  <br/> |
   
**表值**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |可见性。  <br/> |
|2  <br/> |行为。  <br/> |
   
## <a name="see-also"></a>另请参阅

[tblNode](tblnode.md)
