---
title: "更改音频会议网桥的设置"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
description: "Get the steps you need to change settings for a Microsoft dial-in conferencing bridge that's used to prompt callers and gather names and pins for meeting organizers when they're not using Skype for Business clients. "
---

# 更改音频会议网桥的设置

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](783fad3f-b77c-422b-b91f-7c8b0af324fb.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/783fad3f-b77c-422b-b91f-7c8b0af324fb) 中查找本文的英文版本以便参考。
  
设置 Office 365 中的音频会议时，会为您的用户从所谓的音频会议网桥收到电话号码。会议网桥可以包含一个或多个电话号码。呼叫者拨入会议时，使用这些电话号码。电话号码将包括Skype for Business或 Microsoft 小组会议邀请底部。
  
会议网桥应答呼叫，并将呼叫者提示语音提示使用会议自动助理，然后，具体取决于您的设置，可播放通知、 要求呼叫者录制其姓名，然后控制 PIN 设置。Pin 提供给会议组织者以允许他们启动会议时未使用Skype for Business或 Microsoft 小组应用程序。
  
> [!IMPORTANT]
> PIN 只能为所需的会议组织者时Skype for Business或 Microsoft 小组应用用户未已经启动会议。如果每个人都拨入会议，则 PIN 是必需的会议组织者启动会议。 
  
## 更改音频会议网桥的设置

 **当呼叫者加入会议时设置会议体验**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**中，在左侧导航中转到 **音频会议**> **Microsoft 网桥的设置**。
    
4. 在 **Microsoft 网桥设置**页面上的在 **会议加入体验**，下，选择：
    
  - **启用会议进入和退出通知打开**默认情况下选择此选项。如果清除此复选框，则不会收到已加入会议的用户，当有人进入或离开会议。
    
    当您选择 **启用会议进入和退出通知以打开**时，您可以从 **条目/退出通知类型**列表中选择这些选项：
    
  - **名字或电话号码**当用户拨入会议时，在加入它时，将播放其电话号码。
    
  - **色调**当用户拨入会议时，加入它时，将播放音频的色调。
    
    > [!NOTE]
    > 当前所有客户都可以将 **音调**作为通知类型，这是一项预览功能。 
  
  - **要求呼叫者能够录制其姓名之前加入会议**默认情况下选择此选项。如果清除此复选框，不要求呼叫者加入会议之前录制其姓名。
    
5. 完成更改后，单击" **保存**"。
    
 **设置会议 PIN 长度**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**，在左侧导航中，转到 **音频会议**> **Microsoft 网桥的设置**。
    
4. 在 **Microsoft 网桥设置**页面上，在 **安全性**下输入所需的 pin **PIN 长度**列表中的位数，然后单击 **保存**。
    
    > [!IMPORTANT]
    > 4 到 12 位之间必须固定。 
  
 **选择是否向用户发送电子邮件**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**，在左侧导航中，转到 **音频会议**> **Microsoft 网桥的设置**。
    
4. 在 **Microsoft 网桥设置**页面中，选择或清除 **其音频会议配置改变时自动发送给用户的电子邮件**，，然后单击 **保存**。
    
    有关详细信息，请参阅[其音频会议设置更改时自动发送给用户的电子邮件](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md)。
    
## 想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此过程，您可以使用[设置 CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet。
    
- Windows PowerShell 是有关管理用户和允许或不可以执行哪些用户的所有信息。 使用 Windows PowerShell，您可以管理Office 365使用单一管理，当您有多个要执行的任务可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
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

