---
title: Skype for Business Server 2015 中的 ErrorDef 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 表存储可能出现的每种类型的错误的相关信息。 每条记录是一种类型的错误。
ms.openlocfilehash: c6157bb62df47b8fcb1cd158605c5a357e623adf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296278"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ErrorDef 表
 
ErrorDef 表存储可能出现的每种类型的错误的相关信息。 每条记录是一种类型的错误。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Primary  <br/> |标识此类型错误的唯一 ID 号。  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |与此错误相关联的标准 SIP 响应代码。  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft 诊断 ID。  <br/> |
|**CallTypeId** <br/> |整形  <br/> |外表  <br/> |通话的类型。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 CallType 表](calltype.md)。 <br/> |
|**RequestType** <br/> |varbinary (33)  <br/> | <br/> |失败的请求类型。  <br/> 可以使用以下语法将此数据转换为文本格式:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary (257)  <br/> | <br/> |失败的请求的内容类型。  <br/> 可使用此 syntaxt 将此数据转换为文本格式:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

