---
title: "对其音频会议信息的用户发送电子邮件"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
description: "Send your users an email with their dial-in conferencing information."
---

# 对其音频会议信息的用户发送电子邮件

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
有时 Skype 业务或 Microsoft 团队用户可能需要您向他们发送其音频会议信息。通过使用 **Skype for Business 管理中心**，并为用户的属性下，单击 **发送会议信息通过电子邮件**，可以执行此操作。当您发送此电子邮件时，它将包含所有音频会议的信息，包括：
  
- 用户的会议电话或拨入电话号码。
    
- 用户的会议 ID。
    
    > [!NOTE]
    > 当您组织中的人员不想要记住的一个随机数; 使用静态 Id他们可以选择特定数字或使用一个容易记住。当使用动态会议 Id 时，每个会议用户计划将获得分配一个唯一的会议 id。如果您要分配动态而不是静态会议 Id，[在您的组织中使用音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。 
  
下面是发送的电子邮件的示例：
  
![电话拨入式会议电子邮件](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## 向用户发送一封电子邮件与音频会议信息

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到 **Office 365 管理中心**> **Skype for Business**，然后在左侧导航中，单击 **音频会议**。
    
3. 单击 **用户**，然后选择用户。
    
4. 在操作窗格中，单击" **通过电子邮件发送会议信息**"。
    
> [!TIP]
> 您也可以发送电子邮件向用户与音频会议设置通过编辑用户的属性，然后单击 **音频会议**> **发送会议信息通过电子邮件**。 
  
## 此电子邮件的其他须知事项。

- 有多个电子邮件发送到您的组织中的用户启用它们后的音频会议：
    
  - 当 **音频会议**许可证分配给他们。
    
  - 当您手动重置用户的音频会议的 PIN。
    
  - 当你手动重置用户的会议 ID 时。
    
  - 从中删除 **音频会议**许可证的时间。
    
  - 当用户的音频会议提供商从 Microsoft 更改为另一个提供商或 **无**。
    
  - 当用户的音频会议提供商更改为 Microsoft。
    
- 默认情况下，发件人的电子邮件将来自 Office 365，但您可以更改电子邮件地址，并通过使用 Windows PowerShell 和[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) cmdlet 显示名称。要对电子邮件发送给用户的电子邮件地址进行更改，您必须：
    
  - SendEmailFromAddress 参数中输入的电子邮件地址。
    
  - SendEmailOverride 参数设置为 True。
    
  - SendEmailFromDisplayName 参数中输入的电子邮件的显示名称。
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > 如果要更改电子邮件地址信息，你需要确保你的组织的入站电子邮件策略允许来自设置的自定义电子邮件地址的电子邮件。 
  
## 想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用[设置 CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet。
    
    若要向其音频会议信息与用户发送一封电子邮件，请运行以下命令：
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- 进入 Windows PowerShell， Skype for Business Online时，所有有关管理用户和允许或不可以执行哪些用户。使用 Windows PowerShell，您可以管理Office 365使用单一管理，当您有多个要执行的任务可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么您需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 具有许多优于速度、 简单起见和工作效率中的仅使用 Office 365 管理中心中，例如，当您正在进行设置更改为许多用户，一次。了解有关以下主题中的以下优势：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

