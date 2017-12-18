---
title: "启用或禁用发送电子邮件时更改音频会议设置"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
description: "Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. "
---

# 启用或禁用发送电子邮件时更改音频会议设置

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
在启用音频会议时，用户将自动通知通过电子邮件。可能有的时间，但是，当您想要减少发送到 Skype for Business 和 Microsoft 团队用户的电子邮件的数目。在这种情况下，您可以禁用发送电子邮件。
  
如果您禁用发送电子邮件，不会被音频会议的电子邮件发送到您的用户，包括电子邮件的用户启用或禁用对于音频会议，，他们的 PIN 重置，以及会议 ID 和默认会议电话号码的更改时.
  
下面是当他们启用音频会议发送给用户的电子邮件的示例：
  
![电话拨入式会议电子邮件](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## 什么时候向用户发送电子邮件？

- 有多个电子邮件发送到您的组织中的用户启用它们后的音频会议：
    
  - 当 **音频会议**许可证分配给他们。
    
  - 当您手动重置用户的音频会议的 PIN。
    
  - 当你手动重置用户的会议 ID 时。
    
  - 从中删除 **音频会议**许可证的时间。
    
  - 当用户的音频会议提供商从 Microsoft 更改为另一个提供商或 **无**。
    
  - 当用户的音频会议提供商更改为 Microsoft。
    
## 启用或禁用从发送给用户的电子邮件

您可以使用 Skype for Business 管理中心或 Windows PowerShell 以启用或禁用发送给用户的电子邮件。
  
 **使用 for Business 管理中心中的 Skype**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到 **Office 365 管理中心**> **Skype for Business**，然后在左侧导航中，单击 **音频会议**。
    
3. 在 **Microsoft 网桥设置**页面中，选中或清除 **自动将发送给用户的电子邮件，如果更改了其音频会议设置**。
    
4. 单击" **保存**"。
    
    > [!TIP]
    > 您也可以发送电子邮件向用户与音频会议设置通过转到 **音频会议**> **用户**，选择用户，然后单击 **发送会议信息通过电子邮件**。 > 如果执行此操作，将仅包含会议 ID 和会议电话号码，但不是 PIN 发送一封电子邮件。 > 有关详细信息，请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-audio-conferencing-information.md)。 
  
 **使用 Windows PowerShell**
  
- 运行以下操作以禁用发送电子邮件：
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    此 cmdlet 的帮助，请参阅[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)。
    
## 你还需了解哪些信息？

- 禁用自动电子邮件后，您可以手动仍触发 for Business 管理中心使用 Skype 会议 ID 和电话号码与发送一封电子邮件。但是，如果执行此操作，将不会包含 PIN。如果您想要重置 PIN 音频会议并发送电子邮件被禁用，您将需要向用户发送另一种方法中。
    
- 默认情况下，发件人的电子邮件将来自 Office 365，但可以更改的电子邮件地址和显示使用 Windows PowerShell 的名称，也将使用[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet。
    
    > [!NOTE]
    > 如果要更改电子邮件地址信息，你需要确保你的环境的入站电子邮件策略允许来自指定的发件人地址的电子邮件。 
  
  - 在  _SendEmailFromAddress_ 参数中输入电子邮件地址。
    
  - 在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。
    
  - 将  _SendEmailOverride_ 参数设置为 _True_。
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- 可以使用 Skype for Business 管理中心或 Windows PowerShell 禁用向用户发送电子邮件。
    
## 想知道如何使用 Windows PowerShell 进行管理吗？

- 您可以使用这些 cmdlet 节省时间或自动执行此。
    
  - [获取 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [删除 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [获取 CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [获取 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
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

[Office 365 中的电话拨入式会议](../misctopics/dial-in-conferencing-in-office-365.md)

