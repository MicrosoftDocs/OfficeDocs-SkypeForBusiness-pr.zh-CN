---
title: 在业务服务器 2015年的 Skype 的 FileTransfers 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 每个记录都表示一个文件传输会话。
ms.openlocfilehash: 07ab898246efbac623910886000e97037f43ead2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的 FileTransfers 表
 
每个记录都表示一个文件传输会话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主键和外  <br/> |会议请求的时间。 与**SessionIdSeq**配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主键和外  <br/> |以标识会话的 ID 号。 与**SessionIdTime**配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**文件名称** <br/> |nvarchar(256)  <br/> ||文件的名称。  <br/> |
|**FileIdentity** <br/> |唯一标识符  <br/> ||若要区分涉及文件名称相同的文件传输的唯一标识符。  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |Primary  <br/> |用来标识每个后续消息作为与此相关联。  <br/> |
|**接受** <br/> |bit  <br/> ||可以为真或为空。 如果为 TRUE，则拒绝和取消将为 NULL。  <br/> |
|**拒绝** <br/> |bit  <br/> ||可以为真或为空。 如果为 TRUE，则接受和取消将空值。  <br/> |
|**取消** <br/> |bit  <br/> ||可以为真或为空。 如果为 TRUE，接受和拒绝都将为 NULL。  <br/> |
|**LastModifiedTime** <br/> |日期时间  <br/> ||供内部使用监视服务。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   

