---
title: Skype for Business Server 2015 中的 Dialogs 表
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Dialogs 表是一个支持表，用于存储有关对等会话的 DialogID 的信息。
ms.openlocfilehash: c59f3a2d84f4ebed243cba3dbe22f465551cbfaf
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850675"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 Dialogs 表
 
Dialogs 表是一个支持表，用于存储有关对等会话的 DialogID 的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主  <br/> |会话请求的时间;与 SessionIDSeq 结合使用来唯一地标识会话。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主  <br/> |用于标识会话的 ID 号。 与 SessionIDTime 结合使用来唯一地标识会话。  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |ExternalID 的校验和。 此字段用于提高数据库搜索的速度。  <br/> |
|**ExternalId** <br/> |varbinary (775)   <br/> | <br/> |SIP 对话框 ID，存储为二进制文件。 二进制文件的格式为：  <br/> dialog;from-tag;to-tag  <br/> 可以使用以下语法将此数据转换为文本格式：  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

