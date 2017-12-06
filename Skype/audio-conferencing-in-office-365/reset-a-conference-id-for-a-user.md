---
title: "重置用户的会议 ID"
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
- httpsfix
- Strat_SB_PSTN
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
---

# 重置用户的会议 ID

> [!重要信息]
> 本文是由机器翻译的，请参阅[免责声明](6e12242c-55f7-4bf4-90d7-0f36c0326b8e.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/6e12242c-55f7-4bf4-90d7-0f36c0326b8e) 中查找本文的英文版本以便参考。
  
当您的组织未已启用动态会议 Id 时，Skype 为业务或 Microsoft 小组的用户启用为使用 Microsoft 作为提供商的音频会议时，会自动创建的静态会议 ID。此会议 ID 是包含底部的会议邀请以及呼叫者可用于呼叫进入会议的电话拨入电话号码。当用户拨的电话号码时，会议自动助理会要求呼叫者输入此会议 ID，以便他们可以参加会议。
  
> [!注释]
> 如果您的会议提供商联系 Microsoft，默认情况下用户的会议 Id 设置为仅动态中。很遗憾，您将无法在 Skype for Business 管理中心或使用 Windows Powershell 中更改它。您将需要与 Microsoft 支持部门联系。 
  
当您组织中的人员不想要记住的一个随机数; 使用静态 Id他们可以选择特定数字或使用一个容易记住。当使用动态会议 Id 时，每个会议用户计划将获得分配一个唯一的会议 id。如果您要分配动态而不是静态会议 Id，[在您的组织中使用音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。
  
会议 Id 将仅自动设置仅对业务和 Microsoft 团队启用的用户的音频会议 Skype 使用 Microsoft 作为其音频会议提供商。如果您需要重置为使用第三方音频会议提供商 (ACP) 的用户的会议 ID，您将需要手动输入会议 ID 属性页上的用户。
  
## 重置用户的会议 ID

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**中，单击 **音频会议**> **用户**，选择用户，然后单击在 **会议 ID**下的操作窗格中的 **重置**。
    
4. 在 **重置会议 ID？**窗口中，单击 **是**。会议将自动创建 ID 和电子邮件发送给用户使用新会议 id。默认情况下，向用户发送电子邮件，但可以关闭此功能。
    
    > [!注释]
    > 重置会议 ID 后，会向用户发送包含新会议 ID 的电子邮件。此电子邮件将发送到主电子邮件地址，大多数情况下是其 Office 365 邮箱。电子邮件中包含新的会议 ID、默认拨入电话号码以及使用 Skype for Business 会议更新工具更新现有会议的说明。 
  
## 我还需了解哪些信息？

- 您可以通过单击操作窗格中的用户的 **发送会议信息通过电子邮件**中包含的会议 ID 和拨入电话号码的电子邮件中的用户发送的所有会议信息。它不会发送 PIN。
    
- 会议 ID 将包含 7 位，并且您不能更改其长度在 Skype for Business 管理中心，或通过使用 Windows PowerShell。
    
- 重置之后，你可以看到新会议 ID 列在" **会议 ID**"下方。
    
- 当您选择 **用户**页面上的用户可以查看用户的音频会议的会议 ID 底部的 **音频会议**下的操作窗格。
    
- 创建新的会议 ID 后，呼叫者不使用旧的会议 ID。您应通知重新安排现有会议邀请，以确保新会议 ID 添加到邀请的用户。用户可以使用Skype for Business会议工具更新其现有的会议。若要了解如何下载、 安装和运行 Skype 业务会议更新工具，请参阅：
    
  - [Skype for Business 和 Lync 的会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online、 会议迁移工具 （64 位）](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online、 会议迁移工具 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## 想知道如何使用 Windows PowerShell 进行管理吗？

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!注释]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

