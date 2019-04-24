---
title: ErrorDef 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 表存储有关每种类型的可能发生的错误的信息。 每条记录是错误的一种类型。
ms.openlocfilehash: cec601dad24dda522477bfcd7b1e80d0efc45799
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213107"
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
   

