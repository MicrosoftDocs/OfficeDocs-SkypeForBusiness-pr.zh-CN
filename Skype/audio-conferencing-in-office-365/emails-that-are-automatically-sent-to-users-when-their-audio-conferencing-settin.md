---
title: "其音频会议设置更改时自动发送给用户的电子邮件"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
description: "Learn about what information is sent automatically to users by email when their dial-in conferencing settings change. "
---

# 其音频会议设置更改时自动发送给用户的电子邮件

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](1b46da6d-f93a-4cc0-9ae8-af765935b007.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/1b46da6d-f93a-4cc0-9ae8-af765935b007) 中查找本文的英文版本以便参考。
  
电子邮件将被自动发送到处于[设置音频会议 for Skype Business 和 Microsoft 团队](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)的用户使用 Microsoft 作为音频会议提供商。
  
默认情况下，有四种类型的电子邮件将发送到您的用户启用了音频会议。但是，如果您想要限制发送给用户的电子邮件的数目，您可以将其关闭。在 Office 365 中的音频会议将向您的用户发送电子邮件发送电子邮件时：
  
- **音频会议许可证分配给他们或您要向 Microsoft 更改音频会议提供商。**
    
    此电子邮件中包含会议 ID，默认会议电话号码的会议，音频会议 PIN 用户，并说明和链接可以使用 Skype for Business Online 会议更新工具，用于更新现有会议用户。请参阅[分配 Skype for Business 和 Microsoft 团队合作的用户许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)或[将 Microsoft 作为音频会议提供商分配](assign-microsoft-as-the-audio-conferencing-provider.md)。
    
    > [!NOTE]
    > 如果您的组织已启用的动态会议 Id，所有用户的会议的安排他们将具有唯一会议 Id。您可以设置[在您的组织中使用音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。 
  
    下面是此电子邮件的一个示例：
    
     ![Skype for Business 验证许可证](../images/17913e03-8b4a-4563-b58d-2f09b65fbcaa.png)
  
    您可以了解更多有关 Skype for Business 许可通过查看[Skype for Business 和 Microsoft 团队许可加载项](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
- **会议 ID 或用户默认会议电话号码更改。**
    
    此电子邮件包含用于 Skype for Business Online 会议更新工具，用于更新现有用户的会议的会议 ID、 默认会议电话号码，以及说明和链接。但这封电子邮件不包括用户的音频会议的 PIN。请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。
    
    > [!NOTE]
    > 如果您的组织已启用的动态会议 Id，所有用户的会议的安排他们将具有唯一会议 Id。您可以设置[在您的组织中使用音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。 
  
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议信息已更改。](../images/d6d3e028-d9fb-48c4-97c0-a73d6ade5ea3.png)
  
- **重置音频会议的用户的 PIN。**
    
    此电子邮件包含组织者的音频会议 PIN、 现有会议 ID 和默认会议电话号码的用户。请参阅[重置用户的音频会议 PIN](reset-the-audio-conferencing-pin-for-a-user.md)。
    
    > [!NOTE]
    > 如果您的组织已启用的动态会议 Id，所有用户的会议的安排他们将具有唯一会议 Id。您可以设置[在您的组织中使用音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。 
  
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议 PIN 已更改。](../images/df8df4f8-d11f-41b8-9187-99e66a88831b.png)
  
- **删除用户的许可证更改时或音频会议提供商从 Microsoft 到其他提供商或无。**
    
    当设置为 **无**提供程序时， **音频会议**许可证将被删除的用户时将用户的音频会议提供商从 Microsoft 更改为第三方音频会议提供商或时，将发生这种情况。此电子邮件包含说明和信息的用户使用 Skype for Business Online 会议更新工具来删除音频会议的特定信息，如默认会议电话号码或会议 id。
    
    请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)或[分配第三方音频会议提供商为](assign-a-third-party-as-the-audio-conferencing-provider.md)。
    
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议已关闭。](../images/4ebc8ae6-b516-452e-8d27-6177e145daba.png)
  
## 更改发送给用户的电子邮件

自动发送给包括电子邮件地址和 *从*  联系人信息中包括的显示名称的用户的电子邮件，您可以进行更改。默认情况下，发件人的电子邮件将从 Office 365，但您可以更改电子邮件地址，并显示名称使用 Windows PowerShell 和[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet。要向用户发送电子邮件的电子邮件地址进行更改，您必须：
  
- 在  _SendEmailFromAddress_ 参数中输入电子邮件地址。
    
- 在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。
    
- 将  _SendEmailOverride_ 参数设置为 _True_。
    
通过运行发送给用户，如电子邮件中发送的电子邮件地址和电子邮件的显示名称的电子邮件，可以进行更改：
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
> 如果要更改电子邮件地址信息，你需要确保你的环境的入站电子邮件策略允许来自指定的发件人地址的电子邮件。 > 如果你决定覆盖" *发件人*  "联系信息，你应该验证电子邮件是否正确发送到用户。 你可以通过与你组织中的一个用户进行相关测试，以执行此操作。
  
[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 可用于管理您的组织，包括电子邮件的其他设置。
  
## 如果不想向用户发送电子邮件，又该怎样做？

禁用向用户发送电子邮件时，即使用户获取被分配一个许可证，将不会发送电子邮件。在本例中为会议 ID，默认会议电话号码，并更重要的是，不会向用户发送其音频会议的 PIN。当发生这种情况时，您必须告诉用户通过向他们发送单独的电子邮件或通过调用它们。
  
默认情况下电子邮件将被发送到您的用户，但如果您想要防止接收音频会议的电子邮件，您可以使用 Skype for Business 管理中心或 Windows PowerShell。
  
 **使用 for Business 管理中心中的 Skype**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**，在左侧导航中，转到 **音频会议**> **Microsoft 网桥的设置**。
    
4. 在 **Microsoft 网桥设置**页面中，选中或清除 **自动将发送给用户的电子邮件，如果更改了其音频会议设置**。
    
5. 单击" **保存**"。
    
 **使用 Windows PowerShell**
  
1. 运行以下操作以禁用向你的用户发送所有电子邮件：
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 可用于管理您的组织，包括电子邮件的其他设置。
  
## 此电子邮件的其他须知事项。

- 有关更多有关启用和禁用自动向用户发送电子邮件，请参阅[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md)。
    
- 有时用户丢失其音频的信息，您需要能够向他们发送的所有其音频信息它们。通过使用 for Business 管理中心中的 Skype 用户的音频会议属性下，单击 **发送会议信息通过电子邮件**，可以执行此操作。请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-audio-conferencing-information.md)。但是，该信息不包含音频会议的 PIN。
    
    下面是将发送给用户的电子邮件的一个示例：
    
     ![电话拨入式会议电子邮件](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## 想知道如何使用 Windows PowerShell 进行管理吗？

- 默认情况下，发件人的电子邮件将从 Office 365，但您可以更改电子邮件地址，并显示名称使用 Windows PowerShell 和[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet。
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么您需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 具有许多优于速度、 简单起见和工作效率中的仅使用 Office 365 管理中心中，例如，当您正在进行设置更改为许多用户，一次。 了解有关以下主题中的以下优势：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  
## 另请参阅
<a name="MT_Footer"> </a>

#### 其他资源

[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md)
  
[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-audio-conferencing-information.md)

