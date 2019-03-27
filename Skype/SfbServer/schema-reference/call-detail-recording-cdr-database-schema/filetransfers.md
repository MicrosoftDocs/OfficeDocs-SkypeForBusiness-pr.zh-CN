---
title: FileTransfers 视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: 文件传输视图存储有关对等文件传输会话的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: a39e00becd772e74eb12de1a8ce5975e6626cffa
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881463"
---
# <a name="filetransfers-view"></a>FileTransfers 视图
 
文件传输视图存储有关对等文件传输会话的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
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
   

