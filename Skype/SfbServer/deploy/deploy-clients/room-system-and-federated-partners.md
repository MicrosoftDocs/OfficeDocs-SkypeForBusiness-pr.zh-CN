---
title: Skype 会议室系统和 Skype for Business 联盟伙伴
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: 阅读本主题，了解如何为 Skype for Business 联盟伙伴设置 Skype 会议室系统。
ms.openlocfilehash: ac0203479907f830f1bc6cec6831f8804906e669
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820802"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 会议室系统和 Skype for Business 联盟伙伴
 
阅读本主题，了解如何为 Skype for Business 联盟伙伴设置 Skype 会议室系统。
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 会议室系统和 Skype for Business 联盟伙伴

Skype 会议室系统依赖于日历会议请求中的"加入 Skype for Business 会议"链接。 加入链接通常位于会议请求的正文中。 但是，Skype 会议室系统依赖于此链接以存在于邮件的 MAPI 属性中。 当此会议请求发送到 skype for Business 联盟 (的远程组织) ，默认情况下，远程组织的 Skype 会议室系统不会在日历上显示与会链接。 事实上，远程组织的任何 Outlook 用户都将无法通过右键单击日历项目或在会议提醒中加入 Skype for Business 会议。 他们必须打开会议邀请，并单击邮件正文中的"加入 Skype for Business 会议"。 
  
此限制的原因是 Outlook 和 Microsoft Exchange 不使用特殊方法将信息打包以通过 Internet 发送邮件。 对于从 Exchange 组织外部发送 (TNEF) ，此方法（称为传输中性封装格式）默认处于禁用状态。 若要在远程 Skype 会议室系统上显示与会链接，发送组织必须使用以下命令启用 TNEF：
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

为远程组织启用 TNEF 后，通过 Internet 发送到组织的任何邮件都作为 TNEF 格式的附件发送。 启用 TNEF 后，当 Skype for Business 会议请求发送到 Skype for Business 联盟伙伴时，Skype 会议室系统将能够呈现加入 Skype for Business 会议，远程用户将能够加入 Skype for Business 会议。 
