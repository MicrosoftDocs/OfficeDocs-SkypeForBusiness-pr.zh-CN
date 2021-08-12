---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute 是一个硬编码表，包含用于节点表的 Visibility 和 Behavior 属性。
ms.openlocfilehash: 6996c95ca170082ec89ac7d8fd92648b60c933b1fd72515bb7c3974df8cd5e92
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337580"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute 是一个硬编码表，包含用于节点表的 Visibility 和 Behavior 属性。
  
**Columns**

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
