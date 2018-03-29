---
title: FileTransfers 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTranfer 视图存储有关对等文件传输会话信息。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 69b986c24a3a8f3646738eb3e1e3e97794be8e9e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="filetransfers-view"></a>FileTransfers 视图
 
FileTranfer 视图存储有关对等文件传输会话信息。 在 Microsoft Lync Server 2013 引入了此视图。
  
> [!NOTE]
> FileTransfers 视图它包含[SessionDetails 视图](sessiondetails-0.md)中的列的所有除了下面列出的列。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**文件名** <br/> |nvarchar(256)  <br/> |传输的文件的名称。  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |用来标识每个后续消息作为与此相关联。  <br/> |
|**FileIdentity** <br/> |唯一标识符  <br/> |若要区分涉及文件名称相同的文件传输的唯一标识符。  <br/> |
|**接受** <br/> |bit  <br/> |可以为真或为空。 如果为 TRUE，则拒绝和取消将为 NULL。  <br/> |
|**拒绝** <br/> |bit  <br/> |可以为真或为空。 如果为 TRUE，则接受和取消将空值。  <br/> |
|**取消** <br/> |bit  <br/> |可以为真或为空。 如果为 TRUE，接受和拒绝都将为 NULL。  <br/> |
   

