---
title: "打开或关闭会议的进入和退出通知"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
description: "Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. "
---

# 打开或关闭会议的进入和退出通知

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
当您设置 Office 365 中的音频会议时，您将收到音频会议网桥。会议网桥可以包含一个或多个用户将用于拨入 Skype for Business 或 Microsoft 小组会议的电话号码。
  
会议网桥的会议使用电话拨入用户应答呼叫。会议网桥解答语音提示与呼叫者从会议自动助理，然后，具体取决于您的设置，可以播放通知，请咨询呼叫者录制其姓名，并设置 PIN 安全。PIN 给予业务或 Microsoft 小组会议组织者 Skype 并允许它们在启动时不能使用 Skype for Business 或 Microsoft 团队应用会议启动会议。但是，可以设置它以便 PIN 不需要启动会议。
  
## 设置会议加入选项

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**，在左侧导航中，转到 **音频会议**> **Microsoft 网桥的设置**。
    
4. 在 **会议加入体验**，下中，选中或清除 **启用会议进入和退出通知以打开**。 默认情况下选择此选项。如果清除它，则不会收到已加入会议的用户，当有人进入或离开会议。
    
5. 下 **输入/退出通知类型**，选择 **姓名或电话号码**或 **色调**。
    
6. 选中或取消选中 **要求呼叫者能够录制其姓名之前加入会议**。
    
7. 完成更改后，单击" **保存**"。
    
## 想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用[设置 CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet。
    
- 进入 Windows PowerShell， Skype for Business Online时，所有有关管理用户和允许或不可以执行哪些用户。 使用 Windows PowerShell，您可以管理Office 365使用单一管理，当您有多个要执行的任务可以简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么您需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 具有许多优于速度、 简单起见和工作效率中的仅使用 Office 365 管理中心中，例如，当您正在进行设置更改为许多用户，一次。了解有关以下主题中的以下优势：
    
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

