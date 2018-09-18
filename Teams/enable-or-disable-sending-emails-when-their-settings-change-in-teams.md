---
title: 在 Microsoft Teams 中启用或禁用在音频会议设置更改时发送电子邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解如何在 Microsoft Teams 中启用或禁用 Skype 在 PIN 等设置更改或默认会议号码更改时向用户发送电子邮件。 '
ms.openlocfilehash: a59553f26ee39e042fa28d9e58e7f5ae2aae21be
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23892499"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>在 Microsoft Teams 中启用或禁用在音频会议设置更改时发送电子邮件

为用户启用了音频会议时，会自动通过电子邮件向其发送通知。 但是，有时候你可能希望减少向 Microsoft Teams 用户发送的电子邮件数量。 在这种情况下，你可以禁用发送电子邮件。
  
如果禁用发送电子邮件，则不会向用户发送音频会议电子邮件，包括以下情况的电子邮件：为用户启用或禁用了音频会议时、重置其 PIN 时以及当会议 ID 和默认会议电话号码更改时。
  
下面是为用户启用了音频会议时向用户发送的电子邮件示例：
  
![音频会议电子邮件](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>什么时候向用户发送电子邮件？

- 在为贵组织中的用户启用了音频会议后，会向他们发送多封电子邮件：
    
  - 向其分配**音频会议**许可证时。
    
  - 当你手动重置用户的音频会议 PIN 时。
    
  - 当你手动重置用户的会议 ID 时。
    
  - 删除其**音频会议**许可证时。
    
  - 当用户的音频会议提供商从 Microsoft 更改为另一个提供商或“**无**”时。
    
  - 当用户的音频会议提供商更改为 Microsoft 时。


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>启用或禁用向用户发送电子邮件

你可以使用 Microsoft Teams 或 Windows PowerShell 启用或禁用向用户发送电子邮件。

![teams-logo-30x30.png](media/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**
1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在“**会议网桥**”页面顶部，单击“**网桥设置**”。 

3. 在“**网桥设置**”窗格中，启用或禁用“**当用户的拨入设置更改时自动向用户发送电子邮件**”。

4. 单击“**保存**”。

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**使用 Windows PowerShell**
  
有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。

    
## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。
    
  
## <a name="related-topics"></a>相关主题

[用户的音频会议设置更改时向其发送的电子邮件](emails-sent-to-users-when-their-settings-change-in-teams.md)

[向用户发送包含其音频会议信息的电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


