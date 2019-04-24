---
title: FileTransfers 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 每条记录代表一个文件传输会话。
ms.openlocfilehash: fe95db4e023dfb25158cf0bdf1b07f147abe6bd6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213100"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>FileTransfers 表中的业务服务器 2015 Skype
 
每条记录代表一个文件传输会话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、 外  <br/> |会话请求的时间。 与**SessionIdSeq**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、 外  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**文件名** <br/> |nvarchar(256)  <br/> ||文件的名称。  <br/> |
|**FileIdentity** <br/> |唯一标识符  <br/> ||来区分涉及同一文件名的文件传输的唯一标识符。  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |Primary  <br/> |用于标识与此关联时每个后续消息。  <br/> |
|**接受** <br/> |bit  <br/> ||可以是 TRUE 或 NULL。 如果为 TRUE，则拒绝和取消将为 NULL。  <br/> |
|**拒绝** <br/> |bit  <br/> ||可以是 TRUE 或 NULL。 如果为 TRUE，接受和取消都将为 NULL。  <br/> |
|**取消** <br/> |bit  <br/> ||可以是 TRUE 或 NULL。 如果为 true，则接受和拒绝都将为 NULL。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   

