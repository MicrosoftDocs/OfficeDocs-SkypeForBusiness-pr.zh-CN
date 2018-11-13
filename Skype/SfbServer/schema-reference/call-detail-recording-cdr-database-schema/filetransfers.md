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
description: FileTranfer 视图存储有关对等文件传输会话的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 5b7369769d8091aa3354ea364c7073dfa388986f
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296408"
---
# <a name="filetransfers-view"></a>FileTransfers 视图
 
FileTranfer 视图存储有关对等文件传输会话的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
> [!NOTE]
> FileTransfers 视图还包含[SessionDetails view](sessiondetails-0.md)中的列的所有中下面列出的列。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |传输文件的名称。  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |用于标识与此关联时每个后续消息。  <br/> |
|**FileIdentity** <br/> |唯一标识符  <br/> |来区分涉及同一文件名的文件传输的唯一标识符。  <br/> |
|**接受** <br/> |bit  <br/> |可以是 TRUE 或 NULL。 如果为 TRUE，则拒绝和取消将为 NULL。  <br/> |
|**拒绝** <br/> |bit  <br/> |可以是 TRUE 或 NULL。 如果为 TRUE，接受和取消都将为 NULL。  <br/> |
|**取消** <br/> |bit  <br/> |可以是 TRUE 或 NULL。 如果为 true，则接受和拒绝都将为 NULL。  <br/> |
   

