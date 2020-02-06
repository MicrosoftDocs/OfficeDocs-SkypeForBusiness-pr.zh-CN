---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute 是一个硬编码表，其中包含在节点表中使用的 Visibility 和行为属性。
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814610"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute 是一个硬编码表，其中包含在节点表中使用的 Visibility 和行为属性。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint，not null  <br/> |属性的 ID。  <br/> |
|attributeName  <br/> |nvarchar （256），not null  <br/> |属性的名称。  <br/> |
   
**Key**

|**列**|**说明**|
|:-----|:-----|
|attributeID  <br/> |主键。  <br/> |
   
**表值**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |了解.  <br/> |
|ppls-2  <br/> |现象.  <br/> |
   
## <a name="see-also"></a>另请参阅

[tblNode](tblnode.md)
