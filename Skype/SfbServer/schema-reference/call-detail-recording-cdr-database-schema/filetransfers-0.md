---
title: Skype for Business Server 2015 中的 FileTransfers 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 每条记录表示一个文件传输会话。
ms.openlocfilehash: 8b287d2fc2c40fe7e20cb3abc4ed6e403da701b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815210"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 FileTransfers 表
 
每条记录表示一个文件传输会话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外部  <br/> |会话请求的时间。 与**SessionIdSeq**结合使用以唯一标识会话。 有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外部  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用以唯一标识会话。 有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**文件名** <br/> |nvarchar(256)  <br/> ||文件的名称。  <br/> |
|**FileIdentity** <br/> |标识符  <br/> ||唯一标识符，用于区分涉及相同文件名的文件传输。  <br/> |
|**票证** <br/> |nvarchar  <br/> |Primary  <br/> |用于标识要与此邮件关联的每个后续消息。  <br/> |
|**容纳** <br/> |bit  <br/> ||可以为 TRUE 或 NULL。 如果为 TRUE，则 "拒绝" 和 "取消" 将为 NULL。  <br/> |
|**&** <br/> |bit  <br/> ||可以为 TRUE 或 NULL。 如果为 TRUE，则 "接受" 和 "取消" 将为 NULL。  <br/> |
|**取消** <br/> |bit  <br/> ||可以为 TRUE 或 NULL。 如果为 TRUE，则 "接受" 和 "拒绝" 将为 NULL。  <br/> |
|**LastModifiedTime** <br/> |从中  <br/> ||供监视服务内部使用。  <br/> 此字段是在 Skype for Business Server 2015 中引入的。  <br/> |
   

