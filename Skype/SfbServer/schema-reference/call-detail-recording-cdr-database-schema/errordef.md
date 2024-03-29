---
title: Skype for Business Server 2015 中的 ErrorDef 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 表存储有关每种可能发生的错误类型的信息。 每条记录都是一种类型的错误。
ms.openlocfilehash: e244a8740e8d904d9823fe64842f1a4f2e7fd4d1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391854"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ErrorDef 表
 
ErrorDef 表存储有关每种可能发生的错误类型的信息。 每条记录都是一种类型的错误。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |主  <br/> |标识此类型错误的唯一 ID 号。  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |与此错误关联的标准 SIP 响应代码。  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft 诊断 ID。  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Foreign  <br/> |呼叫的类型。 有关详细信息，请参阅 [Skype for Business Server 2015 中的 CallType](calltype.md) 表。 <br/> |
|**RequestType** <br/> |varbinary (33)   <br/> | <br/> |失败的请求的类型。  <br/> 可以使用以下语法将此数据转换为文本格式：  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary (257)   <br/> | <br/> |失败的请求的内容类型。  <br/> 可以使用以下语法将该数据转换为文本格式：  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

