---
title: Skype会议室系统和Skype for Business联盟伙伴
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: 阅读本主题，了解如何为联盟Skype设置Skype for Business系统。
ms.openlocfilehash: 57c143559af533e1a2a8ef6577a1fe6e9f9de660
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771664"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype会议室系统和Skype for Business联盟伙伴
 
阅读本主题，了解如何为联盟Skype设置Skype for Business系统。
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype会议室系统和Skype for Business联盟伙伴

Skype会议室系统依赖于日历会议Skype for Business中的"加入会议"链接。 加入链接通常位于会议请求的正文中。 但是，Skype系统依赖于此链接以存在于邮件的 MAPI 属性中。 当此会议请求发送到联盟 (Skype for Business远程组织) ，默认情况下，远程组织的 Skype 会议室系统不会在日历上显示与会链接。 事实上，Outlook组织的任何用户将无法通过右键单击日历项目或从会议提醒中加入 Skype for Business 会议。 他们必须打开会议邀请，并单击Skype for Business正文中的"加入会议"。 
  
此限制的原因是，Outlook和 Microsoft Exchange不使用特殊方法来打包信息以通过 Internet 发送邮件。 对于从组织外部发送 (TNEF) ，此方法（称为传输中性封装格式Exchange禁用。 若要使会议加入链接显示在远程会议室Skype，发送组织必须运行以下命令来启用 TNEF：
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

为远程组织启用 TNEF 后，通过 Internet 发送到组织的任何邮件都作为 TNEF 格式的附件发送。 启用 TNEF 后，当向 Skype for Business 联盟伙伴发送 Skype for Business 会议请求时，Skype 会议室系统将能够呈现加入 Skype for Business 会议，远程用户将能够加入 Skype for Business会议。 
