---
title: Skype for Business Server 2015 中的 FileTransfers 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 每条记录代表一个文件传输会话。
ms.openlocfilehash: 85e284e48d6f8610fee9be71c91c368f2dab6988
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404574"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 FileTransfers 表
 
每条记录代表一个文件传输会话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外  <br/> |会话请求的时间。 与 **SessionIdSeq** 结合使用来唯一地标识会话。 有关详细信息[，请参阅 Skype for Business Server 2015 中的 Dialogs](dialogs.md) 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外  <br/> |用于标识会话的 ID 号。 与 **SessionIdTime** 结合使用来唯一地标识会话。 有关详细信息[，请参阅 Skype for Business Server 2015 中的 Dialogs](dialogs.md) 表。 <br/> |
|**File Name** <br/> |nvarchar (256)   <br/> ||文件的名称。  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||用于区分涉及同一文件名的各个文件传输的唯一标识符。  <br/> |
|**Cookie** <br/> |nvarchar (128)   <br/> |主  <br/> |用于标识与此关联时的每条后续消息。  <br/> |
|**Accept** <br/> |bit  <br/> ||可以是 TRUE 或 NULL。如果是 TRUE，则拒绝和取消将为 NULL。  <br/> |
|**Reject** <br/> |bit  <br/> ||可以是 TRUE 或 NULL。如果是 TRUE，则接受和取消将为 NULL。  <br/> |
|**Cancel** <br/> |bit  <br/> ||可以是 TRUE 或 NULL。如果是 TRUE，则接受和拒绝将为 NULL。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 此字段是在 2015 年 Skype for Business Server引入的。  <br/> |
   

