---
title: 其设置更改时向用户发送的电子邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn about what information is sent automatically to users by email when their dial-in conferencing settings change. '
ms.openlocfilehash: 47225eff4d7d8bd091b2b7ba9d795c600cbd4b0e
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="emails-sent-to-users-when-their-settings-change"></a>其设置更改时向用户发送的电子邮件

电子邮件将自动发送到[启用了音频会议](set-up-audio-conferencing.md)用户使用 Microsoft 作为音频会议提供商。
  
默认情况下，有四种类型的电子邮件将发送到您的用户启用了音频会议。 但是，如果要限制向用户发送的电子邮件数，你可以将其关闭。 Office 365 中的音频会议将向用户发送电子邮件时的电子邮件：
  
- **音频会议许可证分配给它们或您要更改为 Microsoft 的音频会议提供商。**
    
     此电子邮件包括会议 ID，会议，音频会议的用户和链接说明要用于业务在线会议更新工具，用来更新现有会议的 Skype 的 PIN 的默认会议电话号码用户。 请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)或[分配 Microsoft 作为音频会议提供商](assign-microsoft-as-the-audio-conferencing-provider.md)。
    
    > [!NOTE]
    > [!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。 您可以设置[您的组织中的音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。 
  
    下面是此电子邮件的一个示例：
    
     ![Skype for Business 验证许可证](../images/audio-conferencing-user-enabled.png)
  
    您可以通过查看[加载项业务和 Microsoft 团队授权的 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)许可业务找出有关 Skype 更多信息。
    
- **会议 ID 或用户默认会议电话号码更改。**
    
    此电子邮件包括会议 ID、默认会议电话号码以及使用 Skype for Business Online 会议更新工具为用户更新现有会议的说明和链接。 但此电子邮件不包括用户的音频会议 PIN。 请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。
    
    > [!NOTE]
    > [!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。 您可以设置[您的组织中的音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。 
  
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议信息已更改。](../images/audio-conferencing-info-change.png)
  
- **音频会议用户的 PIN 重置。**
    
    此电子邮件包含组织者的音频会议 PIN、 现有会议 ID 和用户的默认会议电话号码。 请参阅[重置 PIN 的音频会议](reset-the-audio-conferencing-pin.md)。
    
    > [!NOTE]
    > [!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。 您可以设置[您的组织中的音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。 
  
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议 PIN 已更改。](../images/audio-conferencing-pin-has-changed.png)
  
- **删除用户的许可证或音频会议提供商更改时 microsoft 到其他提供程序或无。**
    
    **音频会议**许可证时将删除来自用户或从 Microsoft 更改用户的音频会议提供商，为第三方音频会议提供商时或设置为**无**的提供程序时，将发生这种情况。 此电子邮件包含说明和信息的用户使用的业务联机会议更新工具 Skype 删除音频会议的特定信息，例如默认会议电话号码或会议 id。
    
    请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc)。
    
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议已关闭。](../images/audio-conferencing-turned-off.png)
  
## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>更改发送给用户的电子邮件

您可以对会自动向用户的电子邮件地址和*从*联系人信息中包括的显示名称包括发送的电子邮件进行更改。 默认情况下，电子邮件发件人将从 Office 365，但您可以更改电子邮件地址，并显示名称使用 Windows PowerShell 和[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet。 若要更改向用户发送电子邮件的电子邮件地址，您必须：
  
- 在  _SendEmailFromAddress_ 参数中输入电子邮件地址。
    
- 在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。
    
- _SendEmailOverride_参数设置为_True_。
    
对电子邮件发送给用户，例如从发送电子邮件的电子邮件地址和电子邮件、 的显示名称的运行，您可以进行更改：
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  如果您想要更改的电子邮件地址信息，您需要确保您的环境的入站电子邮件策略允许来自指定发件人地址的自定义的电子邮件。 如果您决定覆盖*从*联系信息，您应验证正确向用户发送电子邮件。 您可以通过测试这与您的组织中的一个用户执行此操作。
  
[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 可用于管理您的组织，包括电子邮件的其他设置。
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>如果不想向用户发送电子邮件，又该怎样做？

当禁用电子邮件发送给用户时，即使用户拥有分配的许可证，也不会向其发送电子邮件。 在此情况下，会议 ID，默认会议电话号码，以及更重要的是，将不会向用户发送其音频会议 PIN。 发生这种情况时，你必须通过向用户发送单独的电子邮件或呼叫他们进行通知。
  
默认情况下将电子邮件发送给用户，但如果您想要阻止其接收电子邮件音频会议，您可以使用 Microsoft 工作组和 Skype 业务管理中心中或 Windows PowerShell。 

![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，转到**会议** > **会议桥**。 

2. 在**会议桥**页的顶部，单击**网桥的设置**。 

3. 在**桥设置**窗格中，启用或禁用**自动发送电子邮件发送给用户，如果其电话拨入式设置更改**。

4. 单击" **保存**"。
  
![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png)  **使用业务管理中心的 Skype**
    
1. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 网桥的设置**。
    
2. 在**Microsoft 网桥的设置**页上，选中或清除**自动发送电子邮件发送给用户，如果其音频会议设置更改**。 
    
3. 单击" **保存**"。 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**使用 Windows PowerShell**
  
1. 运行以下操作以禁用向你的用户发送所有电子邮件：
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 可用于管理您的组织，包括电子邮件的其他设置。
  
## <a name="what-else-should-you-know-about-this-email"></a>此电子邮件的其他须知事项。

- 有关如何启用和禁用自动向用户发送电子邮件的更多信息，请参阅[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-their-settings-change.md)。
    
- 有时用户会丢失其音频的信息，您需要能够它们他们的所有音频信息向他们发送。 您可以通过业务管理中心的使用 Skype 并单击用户的音频会议属性下的**发送会议信息通过电子邮件**来执行此操作。 请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。 但是，此信息不包括音频会议 PIN。
    
    下面是将发送给用户的电子邮件的一个示例：
    
     ![电话拨入式会议电子邮件](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 默认情况下，电子邮件发件人将从 Office 365，但您可以更改电子邮件地址，并显示名称使用 Windows PowerShell 和[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet。
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么您需要使用 Office 365 PowerShell 中](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)
