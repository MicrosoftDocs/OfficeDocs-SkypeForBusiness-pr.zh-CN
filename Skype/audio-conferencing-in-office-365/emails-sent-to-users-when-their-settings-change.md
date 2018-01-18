---
title: "他们设置更改时，向用户发送电子邮件"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn about what information is sent automatically to users by email when their dial-in conferencing settings change. '
ms.openlocfilehash: a7746018a03a69e429eb8a5df4c68c17f29a97df
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="emails-sent-to-users-when-their-settings-change"></a>他们设置更改时，向用户发送电子邮件

电子邮件将自动发送给[启用音频会议](set-up-audio-conferencing.md)的用户通过音频会议提供商作为 Microsoft。
  
默认情况下，有四种类型的电子邮件将发送给您的用户启用了音频会议。 但是，如果您想要限制的电子邮件发送给用户的数量，您可以将其关闭。 Office 365 中的音频会议会将电子邮件发送到用户的电子邮件时：
  
- **音频会议许可分配给他们，或向 Microsoft 更改音频会议提供商时。**
    
     此电子邮件包含会议 ID、 会议、 音频会议针的用户，以及链接说明用于 Skype 业务在线会议更新工具，用来更新现有的会议默认会议电话号码用户。 请参阅[有关业务和 Microsoft 小组许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)或[作为音频会议提供商指定的 Microsoft](assign-microsoft-as-the-audio-conferencing-provider.md)。
    
    > [!NOTE]
    > 如果您的组织已启用动态会议 Id，所有用户的会议，他们计划将拥有唯一的会议 Id。 您可以设置[您的组织中的音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。 
  
    下面是此电子邮件的一个示例：
    
     ![Skype for Business 验证许可证](../images/audio-conferencing-user-enabled.png)
  
    您可以了解更多关于 Skype 业务授权通过查看[附加业务和 Microsoft 小组授权的 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
- **会议 ID 或用户默认会议电话号码更改。**
    
    此电子邮件包含会议 ID、 默认会议电话号码，并指导和链接使用 Skype 业务在线会议更新工具，用来更新现有的用户会议。 但这封电子邮件中不包含用户的音频会议针。 请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。
    
    > [!NOTE]
    > 如果您的组织已启用动态会议 Id，所有用户的会议，他们计划将拥有唯一的会议 Id。 您可以设置[您的组织中的音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。 
  
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议信息已更改。](../images/audio-conferencing-info-change.png)
  
- **音频会议针的用户将被重置。**
    
    此电子邮件包含了组织者的音频会议针、 现有会议 ID 和默认为用户的会议电话号码。 请参阅[重置用户的音频会议 PIN](reset-the-audio-conferencing-pin-for-a-user.md)。
    
    > [!NOTE]
    > 如果您的组织已启用动态会议 Id，所有用户的会议，他们计划将拥有唯一的会议 Id。 您可以设置[您的组织中的音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。 
  
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议 PIN 已更改。](../images/audio-conferencing-pin-has-changed.png)
  
- **移除用户的许可证更改时或音频会议提供商从 Microsoft 与其他提供者或无。**
    
    **音频会议**许可删除后从用户从 Microsoft 更改用户的音频会议提供商，为第三方音频会议提供商时或为**无**设置提供程序时，将发生这种情况。 此电子邮件包含的指令和信息，为用户使用业务联机会议更新工具 Skype 来删除音频会议的特定信息，例如默认会议电话号码或会议 id。
    
    请参阅[分配或删除业务的 Office 365 的许可证](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc)或[分配给第三方音频会议提供商作为](assign-a-third-party-as-the-audio-conferencing-provider.md)。
    
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议已关闭。](../images/audio-conferencing-turned-off.png)
  
## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>更改发送给用户的电子邮件

您可以对电子邮件自动发送给用户的电子邮件地址，并在*从*联系人信息中包含显示名称包括进行更改。 默认情况下，电子邮件的发件人将从 Office 365，但您可以更改的电子邮件地址和显示名称使用 Windows PowerShell 和[一组 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet。 若要将电子邮件发送到用户的电子邮件地址进行更改，您必须：
  
- 在  _SendEmailFromAddress_ 参数中输入电子邮件地址。
    
- 在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。
    
- 将_SendEmailOverride_参数设置为_True_。
    
您可以更改发送给用户，如发送电子邮件的电子邮件地址和电子邮件，显示名称通过运行的电子邮件：
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  如果您想要更改的电子邮件地址信息，您需要确保您的环境的入站电子邮件策略允许来自指定发件人地址的自定义的电子邮件。 如果您决定重写*从*联系人信息，则应验证电子邮件将正常发送给用户。 您可以使用您的组织中的一个用户测试这这样做。
  
可以使用[一组 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 来管理您的组织，包括电子邮件的其他设置。
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>如果不想向用户发送电子邮件，又该怎样做？

禁用对用户发送电子邮件时，即使用户获取分配许可证将不会发送电子邮件。 在此情况下，会议 ID 中，默认的会议电话号码，并且，更重要的是，不会向用户发送其音频会议针。 发生这种情况，您必须告诉用户通过发送单独的电子邮件或通过调用它们。
  
默认情况下，电子邮件将发送给您的用户，但如果您想要防止它们接收音频会议的电子邮件，可以使用 Skype 业务管理中心或 Windows PowerShell。 
  
 **使用 Skype 业务管理中心**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 请转到**Office 365 管理中心** > **业务的 Skype**。
    
3. 在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 网桥的设置**。
    
4. 在**Microsoft 桥设置**页上，选中或清除**自动发送电子邮件发送给用户，如果他们的音频会议设置更改**。 
    
5. 单击" **保存**"。 
    
 **使用 Windows PowerShell**
  
1. 运行以下操作以禁用向你的用户发送所有电子邮件：
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

可以使用[一组 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 来管理您的组织，包括电子邮件的其他设置。
  
## <a name="what-else-should-you-know-about-this-email"></a>此电子邮件的其他须知事项。

- 有关如何启用和禁用自动向用户发送电子邮件的更多信息，请参阅[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-their-settings-change.md)。
    
- 有时用户丢失其音频信息，您需要能够发送他们的所有音频信息给他们。 要做到这一点对于业务管理中心使用 Skype 和用户的音频会议属性下，单击**将会议信息通过电子邮件发送**。 请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。 但是，此信息不包括音频会议针。
    
    下面是将发送给用户的电子邮件的一个示例：
    
     ![电话拨入式会议电子邮件](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 默认情况下，电子邮件的发件人将从 Office 365，但您可以更改的电子邮件地址和显示名称使用 Windows PowerShell 和[一组 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet。
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 许多相比具有的优势在速度、 简易性和生产率仅使用 Office 365 管理中心，例如，当将设置更改为许多用户一次。 了解这些优势中的以下主题： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)

