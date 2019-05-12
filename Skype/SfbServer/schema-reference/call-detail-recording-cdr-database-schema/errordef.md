---
title: ErrorDef 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 表存储有关每种类型的可能发生的错误的信息。 每条记录是错误的一种类型。
ms.openlocfilehash: f1edd4595cdd360c0da1e3cd76f5ed4b63ddf46d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901164"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>ErrorDef 表中的业务服务器 2015 Skype
 
ErrorDef 表存储有关每种类型的可能发生的错误的信息。 每条记录是错误的一种类型。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Primary  <br/> |标识此错误类型的唯一 ID 号。  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |与此错误关联的标准 SIP 响应代码。  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft 诊断 id。  <br/> |
|**CallTypeId** <br/> |Int  <br/> |外  <br/> |呼叫类型。 请参阅[CallType 表中的业务服务器 2015 Skype](calltype.md)的详细信息。 <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |失败的请求的类型。  <br/> 使用以下语法，可以是此数据转换为文本格式：  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |失败的请求的内容类型。  <br/> 通过将此类，可以是此数据转换为文本格式：  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

