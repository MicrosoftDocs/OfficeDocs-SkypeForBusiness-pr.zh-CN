---
title: "请参阅、 更改和重置会议 ID 分配给用户"
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
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
---

# 请参阅、 更改和重置会议 ID 分配给用户

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
会议 ID 自动分配给为业务或 Microsoft 小组的用户的 Skype for Office 365 中的音频会议设置和使用 Microsoft 作为音频会议提供商时。分配的会议 ID 可以是静态或动态并发送会议邀请中的计划会议时。
  
当您组织中的人员不想要记住的一个随机数; 使用静态 Id他们可以选择特定数字或使用一个容易记住。当使用动态会议 Id 时，每个会议用户计划将获得分配一个唯一的会议 id。如果您要分配动态而不是静态会议 Id，[在您的组织中使用音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。
  
虽然将自动创建并分配给用户的静态会议 ID，有时可能需要用户不希望使用此实例，并想要将其设置为特定的数字时，或者当您的用户不记得或丢失了其会议 id。您可以使用 Windows PowerShell 和 **Skype for Business 管理中心**以查看、 更改和重置其会议 id。
  
电子邮件将被发送到用户的会议 ID 和默认音频会议电话号码，或者如果您重置会议 ID 将将包括会议 ID，但不是 PIN 发送不同的电子邮件。
  
## 查看和更改会议 Id

### 查看会议 ID

您可以查看其会议 ID，并将其发送给用户。
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**> **音频会议**> **用户**，选择的用户的需求会议 id。
    
4. 在操作页面上，在 **会议 ID**下查找。
    
    > [!TIP]
    > 您可以向中包括的会议 ID 和音频的电话号码后，通过单击 **会议信息通过电子邮件发送**链接选择 **用户**页面上的用户的电子邮件的用户发送的所有会议信息。 
  
    您可以使用 Windows PowerShell 查看用户的会议 ID。若要执行此操作，运行：
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    请参阅[Get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617693 )若要了解有关 cmdlet 的详细信息。
    
### 分配或更改会议 ID

您可以分配，或更改用户的会议 ID，如果有人例如，很容易记住的会议 ID。
  
> [!NOTE]
> Skype for Business 管理中心不能用于编辑已自动创建的会议 ID，但您可以使用 Windows PowerShell 编辑或更改您已经设置的会议 ID。 
  
> 若要编辑或更改用户的会议 ID，请运行以下命令：
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

    > [!TIP]
    > 会议 ID 必须包含 7 位，并且您无法在 Skype for Business 管理中心，或通过使用 Windows PowerShell 中更改它。 
  
### 重置会议 ID

例如，如果用户忘记会议 ID，则你可以重置它。
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**> **音频会议**> **用户**，在 **会议 ID**下，操作窗格中单击 **重置**。
    
4. 在 **重置会议 ID？**窗口中，单击 **是**。会议将自动创建 ID 和电子邮件发送给用户使用新会议 id。
    
    你可以使用 Windows PowerShell 来重置用户的会议 ID。 若要执行此操作，请运行以下命令：
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## 你还需了解哪些信息？

-     > [!IMPORTANT]
    >  创建新的会议 ID 或一个重置后，呼叫者不使用旧的会议 ID。您应通知重新安排现有会议邀请，以确保新会议 ID 添加到邀请的用户。用户可以使用Skype for Business会议迁移工具更新其现有的会议。若要了解如何下载、 安装和运行该工具，请参阅：> [Skype for Business 和 Lync 的会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)> [Skype for Business Online、会议迁移工具（64 位）](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype for Business Online、 会议迁移工具 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
  
- 请参阅[设置 CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )若要了解有关 cmdlet 的详细信息。
    
- 会议 ID 必须满足的长度，以在音频会议网桥设置的位数。不能在会议 Id; 使用按字母顺序或特殊字符可以使用仅数字。
    
- 您音频会议的用户的所有会议 ID 都将默认情况下，7 位，并且不都能更改的位数。
    
- 如果用户进入来自 Microsoft 的音频会议提供商为第三方音频会议提供商或音频会议提供商设置为 **无**，将不再工作会议 ID。请参阅[分配第三方音频会议提供商为](assign-a-third-party-as-the-audio-conferencing-provider.md)或[移动到 Microsoft 的用户的音频会议提供商](moving-a-user-s-audio-conferencing-provider-to-microsoft.md)。
    
## 想知道如何使用 Windows PowerShell 进行管理吗？

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 相关主题

[设置音频会议 for Skype Business 和 Microsoft 团队](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

