---
title: FileTransfers 视图
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer 视图存储有关对等文件传输会话的信息。 此视图在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 9a3b0573d9b4a63670c929e5c6080e94e498ff0d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603801"
---
# <a name="filetransfers-view"></a>FileTransfers 视图
 
FileTransfer 视图存储有关对等文件传输会话的信息。 此视图在 Microsoft Lync Server 2013 中引入。
  
> [!NOTE]
> FileTransfers 视图包含 [SessionDetails](sessiondetails-0.md) 视图中的所有列以及下面列出的列。
  
|**列**|**数据类型**|**Details**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar (256)   <br/> |文件传输的名称。  <br/> |
|**Cookie** <br/> |nvarchar (128)   <br/> |用于标识与此关联时的每条后续消息。  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |涉及相同文件名的文件传输之间标识的唯一标识符。  <br/> |
|**Accept** <br/> |bit  <br/> |可以是 TRUE 或 NULL。如果是 TRUE，则拒绝和取消将为 NULL。  <br/> |
|**Reject** <br/> |bit  <br/> |可以是 TRUE 或 NULL。如果是 TRUE，则接受和取消将为 NULL。  <br/> |
|**Cancel** <br/> |bit  <br/> |可以是 TRUE 或 NULL。如果是 TRUE，则接受和拒绝将为 NULL。  <br/> |
   

