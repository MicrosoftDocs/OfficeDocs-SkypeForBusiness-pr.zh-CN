---
title: Skype for Business Online 中的音频会议设置更改时启用或禁用发送电子邮件
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
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解 Skype 在 pin 或默认会议数等设置发生更改时如何启用或禁用向用户发送的电子邮件。 '
ms.openlocfilehash: 7c9c768dfc8bb01bdcbc8e9f20bec1bd980b1e0d
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23864312"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Skype for Business Online 中的音频会议设置更改时启用或禁用发送电子邮件

> [!Note]
> 如果您想要启用或禁用中的 Microsoft 团队发送电子邮件，请参阅 [Microsoft Teams 中的音频会议设置发生更改时启用或禁用发送电子邮件](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)。

要在 Microsoft Teams 中启用或禁用发送电子邮件，请参阅 Microsoft Teams 音频会议设置发生更改时启用或禁用发送电子邮件 但是有时候，可能你想要减少发送到 Skype for Business 用户的电子邮件数量。 在这种情况下，您可以禁用发送电子邮件。
  
如果禁用发送电子邮件，音频会议电子邮件不会发送给你的用户，包括以下情况的电子邮件：当用户启用或禁用音频会议时、重置其 PIN 时以及当会议 ID 和默认会议电话号码发生更改时。
  
下面是他们启用音频会议时，向用户发送的电子邮件的示例：
  
![音频会议电子邮件](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>什么时候向用户发送电子邮件？

- 在为你的组织中的用户启用音频会议之后，会向他们发送许多电子邮件：
    
  - 向其分配**音频会议**许可证时。
    
  - 手动重置用户的音频会议 PIN 时。
    
  - 手动重置用户的会议 ID 时。
    
  - 删除其**音频会议**许可证时。
    
  - 用户的音频会议提供商从 Microsoft 更改为另一个提供商或**无**时。
    
  - 用户的音频会议提供商更改为 Microsoft 时。


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>启用或禁用向用户发送电子邮件

你可以使用 Skype for Business 管理中心或 Windows PowerShell 启用或禁用向用户发送电子邮件。

 
![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**
    
1. 在 **Skype for Business 管理中心**的左侧导航中，转到**音频会议**。
    
2. 在 **Microsoft 网桥的设置** 页上，选中或清除 **如果用户的音频会议设置更改，自动向他们发送电子邮件**。
    
3. 单击 **保存** 。
    
    > [!TIP]
    > 你也可以通过电子邮件向用户发送音频会议的设置， 方法是转到**音频会议** > **用户**，选择用户，并单击 **通过电子邮件发送会议信息**。  如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。  请参阅[通过电子邮件向用户发送音频会议信息](send-an-email-to-a-user-with-their-dial-in-information.md)。
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**使用 Windows PowerShell**
  
- 运行以下命令以禁用发送电子邮件： 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

     要获取此 cmdlet 的帮助，请参阅 [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)。
    
## <a name="what-else-should-you-know"></a>你还需了解哪些信息？

- 当禁用自动电子邮件时，你仍然可以使用 Skype for Busines 管理中心手动触发包含会议 ID 和电话号码的电子邮件。 但是，如果执行此操作，则不会包含 PIN。 如果要重置音频会议 PIN 并禁用发送电子邮件，则需要通过另一种方式将其发送给用户。
    
- 可以使用 Skype for Business 管理中心或 Windows PowerShell 禁用向用户发送电子邮件。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 可以使用这些 cmdlet 来节省时间或自动执行此操作。
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 与仅使用 Office 365 管理中心相比，Windows PowerShell 在速度、简化程度和工作效率等方面具有许多优点，例如，当一次更改许多用户的设置时。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[用户音频会议设置更改时向其发送的电子邮件](emails-sent-to-users-when-their-settings-change.md)

[通过电子邮件向用户发送音频会议信息](send-an-email-to-a-user-with-their-dial-in-information.md)


