---
title: Skype 会议室系统和 Skype for Business 联盟伙伴
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: 阅读本主题，了解如何为 Skype for Business 联盟伙伴设置 Skype 会议室系统。
ms.openlocfilehash: 30668641f2c43981485531722861647fdeffc710
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895017"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 会议室系统和 Skype for Business 联盟伙伴
 
阅读本主题，了解如何为 Skype for Business 联盟伙伴设置 Skype 会议室系统。
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 会议室系统和 Skype for Business 联盟伙伴

Skype 会议室系统依赖于业务会议链接日历会议请求中的加入 Skype。 加入链接通常可在会议请求的正文中找到。 但是，Skype 会议室系统取决于此链接出现在邮件的 MAPI 属性。 此会议的请求时是发送到远程组织 (Skype 联合的业务合作伙伴的)，默认情况下远程组织的 Skype 会议室系统将不会显示与会日历的链接。 实际上，远程组织中的任何 Outlook 用户将无法加入的日历的右键单击与业务会议 Skype 项目或从会议提醒中。 它们必须打开会议邀请，并单击加入 Skype 的邮件正文中的业务会议。 
  
此限制的原因是 Outlook 和 Microsoft Exchange 不使用特殊方法来打包用于跨 Internet 发送邮件的信息。 对于从 Exchange 组织外部发送的邮件，此方法（称为传输中立封装格式 (TNEF)）默认情况下被禁用。 会议加入链接上远程 Skype 会议室系统，显示发送组织必须使用以下命令来启用 TNEF:
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

在为远程组织启用 TNEF 之后，通过 Internet 发送到该组织的任何邮件都将采用 TNEF 格式作为附件发送。 使用 TNEF 启用时的 Skype, 业务会议请求是发送到的业务联盟伙伴，Skype Skype 会议室系统都将能够加入 Skype 呈现业务会议和远程用户将能够加入 Skype 业务会议。 
