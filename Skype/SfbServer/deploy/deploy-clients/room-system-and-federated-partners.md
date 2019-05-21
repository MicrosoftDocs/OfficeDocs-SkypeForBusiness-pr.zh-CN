---
title: Skype 会议室系统和 Skype for Business 联盟伙伴
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: 阅读本主题，了解如何为 Skype for Business 联盟伙伴设置 Skype 会议室系统。
ms.openlocfilehash: f47659ce1fcf98e026eea3c4a1f38f74575235dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291714"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 会议室系统和 Skype for Business 联盟伙伴
 
阅读本主题，了解如何为 Skype for Business 联盟伙伴设置 Skype 会议室系统。
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 会议室系统和 Skype for Business 联盟伙伴

Skype 会议室系统依赖于日历会议请求中的 "加入 Skype for Business 会议" 链接。 加入链接通常可在会议请求的正文中找到。 但是, Skype 会议室系统依赖于此链接显示在邮件的 MAPI 属性中。 当此会议请求发送到远程组织 (Skype for Business 联盟合作伙伴) 时, 默认情况下, 远程组织的 Skype 会议室系统将不会在日历上显示 "会议加入" 链接。 实际上, 远程组织中的任何 Outlook 用户都无法通过右键单击日历项目或从会议提醒中加入 Skype for Business 会议。 他们必须打开会议邀请, 然后单击邮件正文中的 "加入 Skype for Business 会议"。 
  
此限制的原因是 Outlook 和 Microsoft Exchange 不使用特殊方法来打包用于跨 Internet 发送邮件的信息。 对于从 Exchange 组织外部发送的邮件，此方法（称为传输中立封装格式 (TNEF)）默认情况下被禁用。 若要在远程 Skype 会议室系统上显示会议加入链接, 发送组织必须使用以下命令启用 TNEF:
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

在为远程组织启用 TNEF 之后，通过 Internet 发送到该组织的任何邮件都将采用 TNEF 格式作为附件发送。 启用 TNEF 后, 如果将 Skype for Business 会议请求发送到 Skype for business 联盟合作伙伴, 则 Skype 会议室系统将能够呈现 "加入 Skype for business" 会议, 并且远程用户将能够加入 Skype for business 会议。 
