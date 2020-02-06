---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue 是一个硬编码表，其中包含在节点表中使用的属性的可见性和行为值。
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814600"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue 是一个硬编码表，其中包含在节点表中使用的属性的可见性和行为值。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint，not null  <br/> |值的 ID。  <br/> |
|attributeID  <br/> |smallint，not null  <br/> |属性的 ID。  <br/> |
|attributeValue  <br/> |nvarchar （256），not null  <br/> |值的名称。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|valueID  <br/> |主键。  <br/> |
|attributeID  <br/> |TblEnumAttribute 表中的 lookup 的外键。  <br/> |
   
**表值**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|ppls-2  <br/> |1  <br/> |专用  <br/> |
|3  <br/> |1  <br/> |范畴  <br/> |
|4  <br/> |ppls-2  <br/> |垂直  <br/> |
|5  <br/> |ppls-2  <br/> |auditorium  <br/> |
|6  <br/> |1  <br/> |公开  <br/> |
   
## <a name="see-also"></a>另请参阅

[tblNode](tblnode.md)
