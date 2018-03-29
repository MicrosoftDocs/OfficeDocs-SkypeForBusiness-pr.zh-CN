---
title: Skype 会议室系统和 Skype for Business 联盟伙伴
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: 阅读本主题，了解如何为 Skype for Business 联盟伙伴设置 Skype 会议室系统。
ms.openlocfilehash: 040af495217217b3bfd10fb577b7194df354e027
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 会议室系统和 Skype for Business 联盟伙伴
 
阅读本主题，了解如何为 Skype for Business 联盟伙伴设置 Skype 会议室系统。
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 会议室系统和 Skype for Business 联盟伙伴

Skype 的空间系统依赖于业务会议链接日历会议请求中加入 Skype。 加入链接通常可在会议请求的正文中找到。 但是，Skype 的空间系统取决于消息的 MAPI 属性中存在此链接。 当此会议请求发送到远程组织 (Skype 联合的商业伙伴)，默认情况下远程组织的 Skype 的空间系统将不会显示在日历的会议加入链接。 实际上，远程组织中的任何 Outlook 用户将不能参加商务会议，用右键单击该日历的 Skype 项目，还是从会议提醒内。 他们必须打开会议邀请并单击加入 Skype 在邮件正文中的商务会议。 
  
此限制的原因是 Outlook 和 Microsoft Exchange 不使用特殊方法来打包用于跨 Internet 发送邮件的信息。 对于从 Exchange 组织外部发送的邮件，此方法（称为传输中立封装格式 (TNEF)）默认情况下被禁用。 会议联接链接出现在远程的 Skype 的空间系统，发送组织必须使用以下命令来启用 TNEF:
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

在为远程组织启用 TNEF 之后，通过 Internet 发送到该组织的任何邮件都将采用 TNEF 格式作为附件发送。 与已启用的 TNEF 时为 Skype, 业务会议请求发送到对商业联盟伙伴，Skype Skype 的空间系统将能够呈现联接 Skype 业务会议和远程用户将能够加入 Skype 业务会议。 