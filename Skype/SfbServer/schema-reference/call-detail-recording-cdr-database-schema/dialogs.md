---
title: Skype for Business Server 2015 中的 Dialogs 表
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
ms.localizationpriority: medium
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Dialogs 表是一个支持表，用于存储有关对等会话的 DialogID 的信息。
ms.openlocfilehash: 6f5abd6326ca1f00a631462c43c8814fb3822f41
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580426"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 Dialogs 表
 
Dialogs 表是一个支持表，用于存储有关对等会话的 DialogID 的信息。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主  <br/> |会话请求的时间;与 SessionIDSeq 结合使用来唯一地标识会话。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主  <br/> |用于标识会话的 ID 号。 与 SessionIDTime 结合使用来唯一地标识会话。  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |ExternalID 的校验和。 此字段用于提高数据库搜索的速度。  <br/> |
|**ExternalId** <br/> |varbinary (775)   <br/> | <br/> |SIP 对话框 ID，存储为二进制文件。 二进制文件的格式为：  <br/> dialog;from-tag;to-tag  <br/> 可以使用以下语法将此数据转换为文本格式：  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

