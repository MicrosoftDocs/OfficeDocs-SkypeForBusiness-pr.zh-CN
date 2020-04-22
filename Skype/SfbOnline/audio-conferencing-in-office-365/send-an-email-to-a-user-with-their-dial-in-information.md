---
title: 使用 Skype for Business Online 中的音频会议向用户发送电子邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 在 Skype for business Online 中向用户发送其音频会议信息的电子邮件。
ms.openlocfilehash: b499bfb4734d46a671ff4c236b354630f7e0a284
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776807"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>通过 Skype for Business Online 中的音频会议信息向用户发送电子邮件

> [!Note]
> 有关向 Microsoft 团队中的用户发送音频会议信息的信息，请参阅[使用 Microsoft Teasms 中的音频会议信息向用户发送电子邮件](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams)。

有时，Skype for business 用户可能需要你向其发送音频会议信息。 你可以通过使用**Skype For business 管理中心**，然后单击用户的 "属性" 下的 "**通过电子邮件发送会议信息**" 来执行此操作。 发送此电子邮件时，它将包含所有音频会议信息，包括：
  
- 用户的会议电话或拨入电话号码。
    
- 用户的会议 ID。
    
   
下面是已发送电子邮件的示例：
  
![电话拨入式会议电子邮件](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>向用户发送包含音频会议信息的电子邮件

1. 在左侧导航中，单击 "**用户**"，然后从可用用户列表中选择用户。

2. 在页面的顶部，单击**编辑**。

3. 在 "**音频会议**" 下，单击 "**通过电子邮件发送会议信息**"。

1. 使用你的工作或学校帐户登录。
    
2. 转到管理中心 > **Skype for**business，然后在左侧导航中单击 "**音频会议**"。
    
3. 单击 "**用户**"，然后选择用户。
    
4. 在操作窗格中，单击" **通过电子邮件发送会议信息**"。
    
> [!TIP]
> 您还可以通过编辑用户的属性，然后单击 "**音频会议** > **通过电子邮件发送会议信息**"，使用音频会议设置向用户发送电子邮件。 

## <a name="what-else-should-you-know-about-this-email"></a>此电子邮件的其他须知事项。

- 在为您的组织中的用户启用音频会议后，会向他们发送多封电子邮件：
    
  - 向其分配**音频会议**许可证时。
    
  - 当您手动重置用户的音频会议 PIN 时。
    
  - 当你手动重置用户的会议 ID 时。
    
  - 删除**音频会议**许可证后。
    
  - 当用户的音频会议提供商从 Microsoft 更改为另一个提供商或 "**无**" 时。
    
  - 当用户的音频会议提供商更改为 Microsoft 时。
    
- 默认情况下，电子邮件的发件人将来自 Office 365，但你可以使用 Windows PowerShell 和[set-csonlinedialinconferencingtenantsettings](https://go.microsoft.com/fwlink/?LinkId=708983) cmdlet 更改电子邮件地址和显示名称。 若要对向用户发送电子邮件的电子邮件地址进行更改，必须执行以下操作：
    
  - 在 SendEmailFromAddress 参数中输入电子邮件地址。
    
  - 将SendEmailOverride参数设置为 True。
    
  - 在 SendEmailFromDisplayName 参数中输入电子邮件的显示名称。
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > [!注释] 如果要更改电子邮件地址信息，你需要确保你的组织的入站电子邮件策略允许来自设置的自定义电子邮件地址的电子邮件。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet。
    
    若要向用户发送其音频会议信息的电子邮件，请运行以下操作：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- 对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。使用 Windows PowerShell，可以通过单点管理来管理 Office 365，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你为多个用户同时进行设置更改时。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
