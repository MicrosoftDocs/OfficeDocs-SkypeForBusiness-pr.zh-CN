---
title: Skype for Business Server 2015 中的 ErrorDef 表
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 表存储有关可能发生的每种类型的错误的信息。 每条记录都是一种类型的错误。
ms.openlocfilehash: 50d7b76e1fc7edb53fbe0b299673b7281a394463
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821722"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ErrorDef 表
 
ErrorDef 表存储有关可能发生的每种类型的错误的信息。 每条记录都是一种类型的错误。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |主  <br/> |标识此类型错误的唯一 ID 号。  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |与此错误关联的标准 SIP 响应代码。  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft 诊断 ID。  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Foreign  <br/> |呼叫的类型。 有关详细信息， [请参阅 Skype for Business Server 2015](calltype.md) 中的 CallType 表。 <br/> |
|**RequestType** <br/> |varbinary (33)   <br/> | <br/> |失败的请求的类型。  <br/> 可以使用以下语法将此数据转换为文本格式：  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary (257)   <br/> | <br/> |失败的请求的内容类型。  <br/> 可以使用以下语法将数据转换为文本格式：  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

