---
title: 在业务服务器 2015年的 Skype 的 ErrorDef 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 表用来存储有关每种可能发生的错误的信息。 每个记录是错误的一种类型。
ms.openlocfilehash: 4583e1130d257a99d075f2dec0dea80ee6b1390c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的 ErrorDef 表
 
ErrorDef 表用来存储有关每种可能发生的错误的信息。 每个记录是错误的一种类型。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Primary  <br/> |唯一 ID 号标识这种类型的错误。  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |与此错误关联的标准 SIP 响应代码。  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft 诊断程序 id。  <br/> |
|**CallTypeId** <br/> |Int  <br/> |外  <br/> |调用的类型。 [业务服务器 2015年的 Skype 在 CallType 表](calltype.md)的详细信息，请参阅。 <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |失败的请求的类型。  <br/> 此数据可以转换为文本格式，使用以下语法：  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |失败的请求的内容类型。  <br/> 通过使用此 syntaxt，此数据可以转换为文本格式：  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

