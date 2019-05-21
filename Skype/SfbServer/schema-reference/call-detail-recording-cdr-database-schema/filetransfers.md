---
title: FileTransfers 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer 视图存储有关对等文件传输会话的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 303a8cf624b19f9701cabbd491fcb7b08dfba25d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296236"
---
# <a name="filetransfers-view"></a>FileTransfers 视图
 
FileTransfer 视图存储有关对等文件传输会话的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
  
> [!NOTE]
> FileTransfers 视图包含[SessionDetails 视图](sessiondetails-0.md)中的所有列以及下面列出的列。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |已传输的文件的名称。  <br/> |
|**票证** <br/> |nvarchar  <br/> |用于标识要与此邮件关联的每个后续消息。  <br/> |
|**FileIdentity** <br/> |标识符  <br/> |唯一标识符, 用于区分涉及相同文件名的文件传输。  <br/> |
|**容纳** <br/> |bit  <br/> |可以为 TRUE 或 NULL。 如果为 TRUE, 则 "拒绝" 和 "取消" 将为 NULL。  <br/> |
|**&** <br/> |bit  <br/> |可以为 TRUE 或 NULL。 如果为 TRUE, 则 "接受" 和 "取消" 将为 NULL。  <br/> |
|**取消** <br/> |bit  <br/> |可以为 TRUE 或 NULL。 如果为 TRUE, 则 "接受" 和 "拒绝" 将为 NULL。  <br/> |
   

