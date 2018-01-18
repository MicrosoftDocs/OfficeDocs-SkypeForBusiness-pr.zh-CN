---
title: "更改音频会议桥的设置"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
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
description: 'Get the steps you need to change settings for a Microsoft dial-in conferencing bridge that''s used to prompt callers and gather names and pins for meeting organizers when they''re not using Skype for Business clients. '
ms.openlocfilehash: 5da33e083999f00d217a86455f61fd58ca2d1713
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>更改音频会议桥的设置

要设置 Office 365 中的音频会议，将为您的用户从所谓的音频会议网桥收到电话号码。 会议桥可以包含一个或多个电话号码。 调用方拨号加入会议时，将使用这些电话号码。 电话号码是包含在业务或 Microsoft 小组会议邀请的 Skype 的底部。
  
会议桥应答呼叫，并提示调用方通过语音提示使用会议自动助理，然后根据您的设置，它可以播放通知，要求调用方来记录他们的姓名，并控制 PIN 设置。 针脚提供给会议组织者，使他们开始会议时不使用 Skype 业务或 Microsoft 团队的应用程序。

    > [!IMPORTANT]
    > A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting. 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>更改音频会议桥的设置

 **当调用方加入会议设置会议经验**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 请转到**Office 365 管理中心** > **业务的 Skype**。
    
3. 在**业务管理中心的 Skype**，在左边的导航转到**音频会议** > **Microsoft 网桥的设置**。
    
4. 在下**会议连接体验**， **Microsoft 网桥的设置**页，请选择：
    
  - **启用会议进入和退出通知以打开**默认情况下选择此选项。 如果清除复选框，当有人进入或离开会议，不会通知用户已加入会议。
    
    **启用会议进入和退出通知以打开**选择时，您可以从**入口/出口公告类型**列表中选择这些选项：
    
  - **姓名或电话号码**当用户拨号加入会议时，在他们加入时将播放他们的电话号码。
    
  - **拨号音**当用户拨号加入会议时，将它加入后播放音频音调。
    
    > [!NOTE]
    > [!注释] 当前所有客户都可以将 **音调**作为通知类型，这是一项预览功能。
  
  - **提出调用方来记录他们的姓名之前加入会议**默认情况下选择此选项。 如果清除复选框，将不要求调用方之前他们加入会议记录他们的姓名。
    
5. 完成更改后，单击" **保存**"。
    
**设置会议的针长度**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 请转到**Office 365 管理中心** > **业务的 Skype**。
    
3. 在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 网桥的设置**。
    
4. 在**Microsoft 桥设置**页上，在**安全**下，输入 PIN**针长度**列表中，为所需的位数，然后单击**保存**。
    
    > [!IMPORTANT]
    > PIN 必须介于 4 到 12 位。 
  
**选择是否要将电子邮件发送给您的用户**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 请转到**Office 365 管理中心** > **业务的 Skype**。
    
3. 在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 网桥的设置**。
    
4. 在**Microsoft 桥设置**页上，选择或清除**其音频会议配置改变时自动发送电子邮件发送给用户**，，然后单击**保存**。
    
    有关详细信息，请参阅[电子邮件自动发送给用户的音频会议设置更改时](emails-sent-to-users-when-their-settings-change.md)。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 若要节省时间或自动执行此过程，您可以使用[一组 CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet。
    
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

[设置 Skype for Business 和 Microsoft Teams 音频会议](set-up-audio-conferencing.md)

