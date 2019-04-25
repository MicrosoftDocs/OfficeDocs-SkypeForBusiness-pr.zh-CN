---
title: 业务 online 对其 Skype 中的音频会议的用户发送电子邮件
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 您的用户使用他们的音频会议信息的电子邮件中发送 Skype 业务 online。
ms.openlocfilehash: 80cfbd88b8c933e2b1e66d6348deff111a45f8e3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229318"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>对 Skype 中的业务联机其音频会议信息的用户发送电子邮件

> [!Note]
> 有关将音频会议信息发送给 Microsoft 团队中的用户的信息，请参阅[发送给 Microsoft Teasms 其音频会议信息用户电子邮件](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams)。

有时 Skype 业务用户可能需要您向他们发送其音频会议信息。 您可以通过使用**业务管理中心的 Skype**并单击用户属性下的**发送会议信息通过电子邮件**来执行此操作。 当您发送此电子邮件时，它将包含的所有音频会议信息，包括：
  
- 用户的会议电话或拨入电话号码。
    
- 用户的会议 ID。
    
   
下面是发送的电子邮件的示例：
  
![电话拨入式会议电子邮件](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>向用户发送电子邮件与音频会议信息

1. 在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。

2. 在页面的顶部，单击**编辑**。

3. 在**音频会议**，单击**发送电子邮件中的会议信息**。

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到**Office 365 管理中心** > **for Business 的 Skype**，在左侧导航窗格中，单击**要进行音频会议**。
    
3. 单击**用户**，然后选择用户。
    
4. 在操作窗格中，单击" **通过电子邮件发送会议信息**"。
    
> [!TIP]
> 您还可以发送电子邮件向用户使用音频会议设置编辑用户的属性，然后单击**要进行音频会议** > **发送会议信息通过电子邮件**。 

## <a name="what-else-should-you-know-about-this-email"></a>此电子邮件的其他须知事项。

- 有多个电子邮件发送给组织中的用户启用了后为音频会议：
    
  - 向其分配**音频会议**许可证时。
    
  - 当您手动重置用户的音频会议 PIN。
    
  - 当你手动重置用户的会议 ID 时。
    
  - 当**音频会议**许可证已从它们。
    
  - 当用户音频会议提供商从 Microsoft 更改为其他提供程序或**无**。
    
  - 向 Microsoft 更改时用户音频会议提供商。
    
- 默认情况下，电子邮件发件人将从 Office 365，但您可以更改的电子邮件地址，并且可以通过使用 Windows PowerShell 和[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) cmdlet 显示名称。 若要更改向用户发送电子邮件的电子邮件地址，您必须：
    
  - SendEmailFromAddress 参数中输入的电子邮件地址。
    
  - 将SendEmailOverride参数设置为 True。
    
  - SendEmailFromDisplayName 参数中输入的电子邮件显示名称。
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > [!注释] 如果要更改电子邮件地址信息，你需要确保你的组织的入站电子邮件策略允许来自设置的自定义电子邮件地址的电子邮件。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet。
    
    若要向其音频会议信息的用户发送电子邮件，请运行以下命令：
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- 对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。使用 Windows PowerShell，可以通过单点管理来管理 Office 365，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
