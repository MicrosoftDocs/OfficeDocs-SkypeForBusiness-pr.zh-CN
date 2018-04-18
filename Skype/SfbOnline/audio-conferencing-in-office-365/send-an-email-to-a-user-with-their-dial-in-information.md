---
title: 对其拨入信息的用户发送电子邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
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
description: 发送您的用户与他们的音频会议信息的电子邮件。
ms.openlocfilehash: 23eb461d84395672f97fc4ff97c4c0ded7aa92e2
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information"></a>对其音频会议信息的用户发送电子邮件

有时 Skype 业务或 Microsoft 小组用户可能需要您向他们发送他们的音频会议信息。 你可以通过使用**业务管理中心的 Skype** ，并单击用户属性下的**将会议信息通过电子邮件发送**。 当您发送这封电子邮件时，它将包含所有的音频会议信息，包括：
  
- 用户的会议电话或拨入电话号码。
    
- 用户的会议 ID。
    
    > [!NOTE]
    > 当您组织中的人不想记得的随机数; 使用静态标识符他们可以选择一定数量或使用一个容易记住。 当使用动态会议 Id 时，每个会议用户计划将获得分配唯一的会议 id。 如果您想要分配动态而非静态的会议 Id，[转到此处](using-audio-conferencing-dynamic-ids-in-your-organization.md)。 
  
下面是发送的电子邮件的一个示例：
  
![电话拨入式会议电子邮件](../images/audio-conferencing-info.png)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>使用音频会议信息的电子邮件发送给用户

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 请转到**Office 365 管理中心** > **业务的 Skype**，并在左边的导航，请单击**音频会议**。
    
3. 单击**用户**，然后选择用户。
    
4. 在操作窗格中，单击" **通过电子邮件发送会议信息**"。
    
> [!TIP]
> 您还可以发送电子邮件给用户使用音频会议设置通过编辑用户的属性，然后单击**音频会议** > **将会议信息通过电子邮件发送**。 
  
## <a name="what-else-should-you-know-about-this-email"></a>此电子邮件的其他须知事项。

- 有几个之后发送给您的组织中的用户启用音频会议的电子邮件：
    
  - 当**音频会议**许可分配给它们。
    
  - 当您手动重置用户的音频会议针。
    
  - 当你手动重置用户的会议 ID 时。
    
  - 从中删除**音频会议**许可的时间。
    
  - 音频会议提供商为用户更改时由 Microsoft 到另一个提供程序，或**无**。
    
  - 给 Microsoft 更改时用户的音频会议提供商。
    
- 默认情况下，电子邮件的发件人将从 Office 365，但可以更改电子邮件地址，并使用 Windows PowerShell 和[一组 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) cmdlet 显示名称。 若要将电子邮件发送到用户的电子邮件地址进行更改，您必须：
    
  - 在 SendEmailFromAddress 参数中输入电子邮件地址。
    
  - 将 SendEmailOverride 参数设置为 True。
    
  - 在 SendEmailFromDisplayName 参数中输入电子邮件显示名称。
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > [!注释] 如果要更改电子邮件地址信息，你需要确保你的组织的入站电子邮件策略允许来自设置的自定义电子邮件地址的电子邮件。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet。
    
    以电子邮件发送给他们的音频会议信息的用户，运行以下命令：
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。使用 Windows PowerShell，可以通过单点管理来管理 Office 365，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 许多相比具有的优势在速度、 简易性和生产率仅使用 Office 365 管理中心，例如，当将设置更改为许多用户一次。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
