---
title: 更改音频会议网桥的设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.audioconferencing.bridgesettings
ms.custom:
- Audio Conferencing
description: '获取在不使用 Skype for Business 或 Microsoft 团队应用时用于提示呼叫者和收集会议组织者的名称和 pin 的会议桥设置所需的步骤。 '
ms.openlocfilehash: b7ac85729bafe9d27f9e33cfa22597811b8d3d0b
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516948"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>更改音频会议网桥的设置

当您在 Office 365 中设置音频会议时，您将收到来自 "音频会议桥" 的用户的电话号码。一个会议桥可以包含一个或多个电话号码。当呼叫者拨入会议时，将使用这些电话号码。电话号码包含在 Skype for Business 或 Microsoft 团队会议邀请的底部。
  
会议桥应答呼叫，并使用会议自动助理提示呼叫者提供语音提示，然后根据您的设置，它可以播放通知，让呼叫者录制其姓名，并控制固定设置。当会议组织者未使用 Skype for Business 或 Microsoft 团队应用时，将为会议组织者提供允许他们启动会议的 Pin。

  > [!IMPORTANT]
  > 仅当 Skype for Business 或 Microsoft 团队应用用户尚未启动会议时，会议组织者才需要 PIN。如果每个人都在拨入会议，则会议组织者需要 PIN 才能启动会议。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![显示 Microsoft 团队徽标的图标](media/teams-logo-30x30.png) 使用 Microsoft 团队管理中心

1. 在左侧导航中，转到 "**会议** > **桥**"。 

2. 在 "**会议桥**" 页面顶部，单击 "**桥接设置**"。 

3. 在 "**桥设置**" 窗格中，选择： 
   - **会议进入和退出通知**如果关闭此功能，当有人进入或离开会议时，已加入会议的用户不会收到通知。
    
     打开**会议进入和退出通知**时，可以选择以下选项：
    
   - **姓名或电话号码**当用户拨入会议时，将在加入会议时播放其电话号码。
    
   - **声音**当用户拨入会议时，将在加入会议时播放音频音调。
      
   - **邀请呼叫者在加入会议之前录制其姓名**如果关闭此功能，则不会要求呼叫者在加入会议之前记录其名称。

4. 若要设置会议的 PIN 长度，请在 " **pin 长度**" 列表中选择要用于 pin 的数字位数。

5. 若要指定是否向用户发送电子邮件，请启用或禁用**如果用户的音频会议配置发生更改，则自动向用户发送电子邮件**。
    当用户在[Skype For Business Online 中的设置发生更改时](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)，请参阅[自动向用户发送的电子邮件的语音会议设置](emails-sent-to-users-when-their-settings-change-in-teams.md)。
 
6. 单击“**保存**”。 


## <a name="an-icon-showing-the-skype-for-business-logomediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![显示 Skype for Business 徽标的图标](media/sfb-logo-30x30.png)  使用 Skype for Business 管理中心

 **在呼叫者加入会议时设置会议体验**
    
1. 在**Skype for business 管理中心**的左侧导航中，转到 "**音频会议** > **Microsoft 网桥设置**"。
    
2. 在 " **Microsoft bridge 设置**" 页面上的 "**会议加入体验**" 下，选择：
    
   - " **启用会议进入和退出通知**"此选项默认情况下选中。 如果清除该复选框，当有人进入或离开会议时，已加入会议的用户不会收到通知。
    
   - 如果选择 "**启用会议进入和退出通知**"，则可以从 "**输入/退出通知类型**" 列表中选择这些选项：
    
   - **姓名或电话号码**当用户拨入会议时，将在加入会议时播放其电话号码。
    
   - **声音**当用户拨入会议时，将在加入会议时播放音频音调。
  
   - " **要求呼叫者在加入会议之前录制其名称**"此选项默认情况下选中。 如果清除此复选框，则不会要求呼叫者在加入会议之前录制其名称。
    
3. 完成更改后，单击" **保存**"。
    
**设置会议的 PIN 长度**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到**Microsoft 365 管理中心** > **Skype for business**。
    
3. 在**Skype for business 管理中心**的左侧导航中，转到 "**音频会议** > **Microsoft 网桥设置**"。
    
4. 在 " **Microsoft 网桥设置**" 页面上的 "**安全**" 下，在 " **pin 长度**" 列表中输入 pin 所需的数字位数，然后单击 "**保存**"。
    
    > [!IMPORTANT]
    > PIN 必须介于4到12位之间。 
  
**选择是否向你的用户发送电子邮件**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到**Microsoft 365 管理中心** > **Skype for business**。
    
3. 在**Skype for business 管理中心**的左侧导航中，转到 "**音频会议** > **Microsoft 网桥设置**"。
    
4. 在 " **Microsoft 网桥设置**" 页面上，选中或清除 "**如果其拨入信息更改，则自动向用户发送电子邮件**"，然后单击 "**保存**"。
    
    当用户在[Skype For Business Online 中的设置发生更改时](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)，请参阅[自动向用户发送的电子邮件的语音会议设置](emails-sent-to-users-when-their-settings-change-in-teams.md)。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 若要节省时间或自动执行此过程，你可以使用[CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet。
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你为多个用户同时进行设置更改时。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[设置 Microsoft Teams 的音频会议](set-up-audio-conferencing-in-teams.md)

[为 Skype for business Online 设置音频会议](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
