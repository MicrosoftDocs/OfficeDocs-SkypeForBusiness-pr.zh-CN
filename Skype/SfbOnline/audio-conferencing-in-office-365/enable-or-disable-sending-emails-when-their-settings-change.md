---
title: "启用或禁用发送电子邮件，当其设置更改"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 2e8f4975e96531c02cbc2c1a05b4b615829f9205
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a>启用或禁用发送电子邮件时更改音频会议设置

自动通过电子邮件通知用户，当他们启用音频会议。 可能的时间，不过，当您想要减少发送到 Skype 业务和 Microsoft 小组的用户的电子邮件的数量。 在这种情况下，您可以禁用发送电子邮件。
  
音频会议电子邮件如果您禁用发送电子邮件时，将不会发送给您的用户，包括电子邮件的用户启用或禁用音频会议，以及会议 ID 和默认会议电话号码更改时重置其 PIN，.
  
下面是他们启用音频会议时，向用户发送的电子邮件的一个示例：
  
![音频会议电子邮件](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>什么时候向用户发送电子邮件？

- 有几个之后发送给您的组织中的用户启用音频会议的电子邮件：
    
  - 当**音频会议**许可分配给它们。
    
  - 当您手动重置用户的音频会议针。
    
  - 当你手动重置用户的会议 ID 时。
    
  - 从中删除**音频会议**许可的时间。
    
  - 当用户的音频会议提供商从 Microsoft 更改为另一个提供程序，或**无**。
    
  - 给 Microsoft 更改时用户的音频会议提供商。
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a>启用或禁用发送到用户的电子邮件

可以使用业务管理中心为 Skype 或 Windows PowerShell 启用或禁用电子邮件发送给用户。
  
 **使用 Skype 业务管理中心**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 请转到**Office 365 管理中心** > **业务的 Skype**，并在左边的导航，请单击**音频会议**。
    
3. 在**Microsoft 桥设置**页上，选中或清除**自动发送电子邮件发送给用户，如果他们的音频会议设置更改**。
    
4. 单击" **保存**"。
    
    > [!TIP]
    > 您还可以发送电子邮件给用户使用音频会议设置**音频会议**到 > **用户**，选择用户，然后单击**将会议信息通过电子邮件发送**。  如果这样做，将发送一封电子邮件，只包含会议 ID 和会议电话号码，但不是针。  有关详细信息，请参阅[发送一封电子邮件对他们的音频会议信息的用户](send-an-email-to-a-user-with-their-dial-in-information.md)。
  
 **使用 Windows PowerShell**
  
- 运行以下操作来禁用发送电子邮件： 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    此 cmdlet 的帮助信息，请参阅[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)。
    
## <a name="what-else-should-you-know"></a>你还需了解哪些信息？

- 禁用了自动电子邮件，可以手动触发发送一封电子邮件对业务管理中心使用 Skype 的会议 ID 和电话号码。 但是，如果这样做，将不会包含 PIN。 如果您想重置 PIN 音频会议，发送电子邮件被禁用，需要将其发送给用户，以另一种方式。
    
- 默认情况下，电子邮件的发件人将从 Office 365，但可以更改电子邮件地址和显示名称使用 Windows PowerShell 和还使用[一组 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet。
    
    > [!NOTE]
    >  如果您想要更改的电子邮件地址信息，您需要确保您的环境的入站电子邮件策略允许来自指定发件人地址的自定义的电子邮件。
  
  - 在  _SendEmailFromAddress_ 参数中输入电子邮件地址。
    
  - 在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。
    
  - 将_SendEmailOverride_参数设置为_True_。
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- 可以使用 Skype for Business 管理中心或 Windows PowerShell 禁用向用户发送电子邮件。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 这些 cmdlet 可用于节省时间或实现自动操作。
    
  - [获得 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [删除 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [获得 CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [获得 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 许多相比具有的优势在速度、 简易性和生产率仅使用 Office 365 管理中心，例如，当将设置更改为许多用户一次。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[他们的音频会议设置更改时向用户发送电子邮件](emails-sent-to-users-when-their-settings-change.md)

[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)

[设置音频会议 for Skype Business 和 Microsoft 团队](set-up-audio-conferencing.md)
