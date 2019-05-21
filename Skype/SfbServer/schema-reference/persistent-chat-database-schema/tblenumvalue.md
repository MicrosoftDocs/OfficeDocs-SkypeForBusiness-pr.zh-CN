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
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue 是一个硬编码表, 其中包含在节点表中使用的属性的可见性和行为值。
ms.openlocfilehash: bf1ddf75fc7b7fd78c85f47626b465a4d74e5ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295424"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue 是一个硬编码表, 其中包含在节点表中使用的属性的可见性和行为值。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint, not null  <br/> |值的 ID。  <br/> |
|attributeID  <br/> |smallint, not null  <br/> |属性的 ID。  <br/> |
|attributeValue  <br/> |nvarchar (256), not null  <br/> |值的名称。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|valueID  <br/> |主键。  <br/> |
|attributeID  <br/> |TblEnumAttribute 表中的 lookup 的外键。  <br/> |
   
**表值**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |专用  <br/> |
|3  <br/> |1  <br/> |范畴  <br/> |
|4  <br/> |2  <br/> |垂直  <br/> |
|5  <br/> |2  <br/> |auditorium  <br/> |
|6  <br/> |1  <br/> |公开  <br/> |
   
## <a name="see-also"></a>另请参阅

[tblNode](tblnode.md)
