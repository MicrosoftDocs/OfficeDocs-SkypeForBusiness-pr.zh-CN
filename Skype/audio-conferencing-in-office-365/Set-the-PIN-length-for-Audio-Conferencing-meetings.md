---
title: "设置音频会议的 PIN 的长度"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
description: "Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business."
---

# 设置音频会议的 PIN 的长度

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
当您正在设置中的音频会议 for Skype 商业版或 Microsoft 团队时，您将收到音频会议网桥。会议网桥可以包含一个或多个电话号码。设置您的电话号码将包含在会议邀请的 Skype for Business 和 Microsoft 小组的应用程序。
  
音频会议网桥应答的呼叫的人员加入会议使用电话拨入。 从自动助理，然后根据您的设置，它回答语音提示与呼叫者、 可播放通知和要求呼叫者能够录制其姓名。 **Microsoft 网桥设置**允许您更改会议通知的设置和会议加入体验，并设置的由会议组织者 Pin 长度。会议组织者使用 Pin 如果他们无法加入会议使用 Skype for Business 或 Microsoft 团队应用启动会议。
  
## 设置 PIN 长度

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**，在左侧导航中，转到 **音频会议**> **Microsoft 网桥的设置**。
    
4. 在 **安全性**下 > **PIN 长度**，选择所需的 pin，位数，然后单击 **保存**。
    
> [!NOTE]
> PIN 与会议 ID 不同。 会议 ID 由呼叫者在加入会议时使用。 它们用于标识会议。 PIN 用于对作为会议组织者的呼叫者进行身份验证。 
  
## 想要了解有关 PIN 设置的详细信息？

- Pin 可以包含 4 至 12 个数字。默认为 5。创建 Pin 时仅使用的数字。不使用字母和特殊字符。
    
- PIN 只能为所需的会议组织者时Skype for Business或 Microsoft 团队用户未已经启动会议。如果每个人都拨入会议，则需要为会议组织者启动会议 PIN。
    
- PIN 安全设置应用于所有与 Microsoft 网桥相关联的电话号码。他们将应用于使用与给定网桥关联的电话号码的所有会议。
    
## 想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet。
    
- 若要将 PIN 的数字位数设置为 8： `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell 是有关管理用户和允许或不可以执行哪些用户的所有信息。使用 Windows PowerShell，您可以管理Office 365使用单一管理，当您有多个要执行的任务可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么您需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 具有许多优于速度、 简单起见和工作效率中的仅使用 Office 365 管理中心中，例如，当您正在进行设置更改为许多用户，一次。 了解有关以下主题中的以下优势：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
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

[设置音频会议 for Skype Business 和 Microsoft 团队](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)

