---
title: "通过电话不 PIN 的情况下启动音频会议"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
description: "Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. "
---

# 通过电话不 PIN 的情况下启动音频会议

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](d5b1f775-d7ed-4d30-853a-1d49f81e8fde.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/d5b1f775-d7ed-4d30-853a-1d49f81e8fde) 中查找本文的英文版本以便参考。
  
它可能干扰拨入会议以将其保留的在会议厅中收听音乐，因为 Skype for Business 或 Microsoft 团队会议组织者尚未开始会议的用户。
  
如果会议组织者调用中进入会议时，默认情况下，则需要 PIN 启动会议。您可以将其设置，以便所有人都可以拨入会议并不会提示输入 PIN 以启动会议。 您可以使用 Skype for Business 管理中心启用或禁用此设置为单个用户。
  
如果有人开始会议从 Skype for Business 或 Microsoft 团队应用，不需要为会议组织者 PIN。PIN 仅当会议组织者通过电话加入的会议要求。将被分配 **音频会议**许可证并启用了音频会议时，将向音频用户发送的会议的 PIN。请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-audio-conferencing-information.md)和[其音频会议设置更改时自动发送给用户的电子邮件](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md)。
  
## 启用或禁用匿名呼叫者加入会议

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**，在左侧导航中，转到 **音频会议**> **用户**。
    
4. 在列表中，选择用户，然后在操作窗格中，单击 **编辑**。
    
5. 在用户的属性页上，在 **会议选项**中，选中或清除 **允许未经身份验证的呼叫，要在会议中的第一个人员。如果没有，然后他们将在大厅中一直等到经过身份验证的用户加入**。
    
6. 单击" **保存**"。
    
 **若要启用或禁用全部使用 Windows Powershell 的用户的会议的匿名呼叫者**
  
- 请运行以下命令：
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## 你还需了解哪些信息？

- 如果您想要重置 PIN，请参阅[重置用户的音频会议 PIN](reset-the-audio-conferencing-pin-for-a-user.md)。
    
- 如果启用匿名访问，或不需要 PIN 启动会议，则：
    
  - 如果会议未启动 （没有没有人在会议中）： 呼叫者将会询问他是组织者;如果他说的是，他将提示您为自己的 PIN，他输入 PIN 之后，会议的开始和用户将加入会议。
    
  - 如果会议已启动 （其他人已在会议中）： 如果他是组织者，他将永远不会提示您输入 PIN; 不会提示呼叫者已经启动会议，和呼叫者将加入它。
    
- 如果禁用匿名访问，或不需要 PIN 启动会议，则：
    
  - 如果会议未启动 （没有没有人在会议中）： 如果她管理器中，并且她将永远不会提示您输入 PIN，不会提示呼叫者。组织者的设置来关闭，因为会议的开始和匿名呼叫者将加入会议。
    
  - 如果会议已启动 （其他人已在会议中）： 如果她管理器中，并且她将永远不会提示您输入 PIN，不会提示呼叫者; 已经启动会议，和呼叫者将加入它。
    
## 想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或多个用户的自动执行此操作，可以使用[设置 CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet。
    
- 进入 Windows PowerShell， Skype for Business Online时，所有有关管理用户和允许或不可以执行哪些用户。 使用 Windows PowerShell，您可以管理Office 365使用单一管理，当您有多个要执行的任务可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
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
  

