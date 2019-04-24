---
title: tblEnumValue
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblenumvalue 表是一个硬编码表，包含节点表使用的属性的 Visibility 和 Behavior 值。
ms.openlocfilehash: 579b2747ea753b8a701d11dd806178427cbb27b3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212878"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblenumvalue 表是一个硬编码表，包含节点表使用的属性的 Visibility 和 Behavior 值。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint，不为 null  <br/> |值的 ID。  <br/> |
|attributeID  <br/> |smallint，不为 null  <br/> |属性的 ID。  <br/> |
|attributeValue  <br/> |nvarchar (256)，不为 null  <br/> |值的名称。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|valueID  <br/> |主键。  <br/> |
|attributeID  <br/> |在 tblEnumAttribute.attributeID 表中查找的外键。  <br/> |
   
**表值**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |专用  <br/> |
|3  <br/> |1  <br/> |范围  <br/> |
|4  <br/> |2  <br/> |普通  <br/> |
|5  <br/> |2  <br/> |大会堂  <br/> |
|6  <br/> |1  <br/> |打开  <br/> |
   
## <a name="see-also"></a>另请参阅

[tblNode](tblnode.md)
