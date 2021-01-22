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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: 更改音频会议网桥设置，包括进入和退出通知、播放姓名或电话号码、音调和提示呼叫者录制其姓名。
ms.openlocfilehash: 9694ac0cddecc5b00c0df133c5c494e4b5bc0d17
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918698"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>更改音频会议网桥的设置

在 Microsoft 365 或 Office 365 中设置音频会议时，你将从称为音频会议网桥的用户收到电话号码。会议网桥可以包含一个或多个电话号码。呼叫者拨入会议时，会使用这些电话号码。电话号码包含在 Skype for Business 或 Microsoft Teams 会议邀请的底部。
  
会议网桥使用会议自动助理应答呼叫并提示呼叫者语音提示，然后根据你的设置，会议网桥可以播放通知、让呼叫者录制其姓名并控制 PIN 设置。PIN 被赋予会议组织者，以便他们在没有使用 Skype for Business 或 Microsoft Teams 应用时启动会议。

  > [!IMPORTANT]
  > 只有当 Skype for Business 或 Microsoft Teams 应用用户尚未启动会议时，会议组织者才需要 PIN。如果每个人都拨入会议，会议组织者需要 PIN 才能启动会议。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) 使用 Microsoft Teams 管理中心

1. 在左侧导航栏中，转到 **"会议**  >  **网桥"。** 

2. 在"会议网桥"**页面顶部**，单击"网桥 **设置"。** 

3. 在" **网桥设置"** 窗格中，选择： 
   - **会议进入和退出通知** 如果关闭此功能，则当某人进入或离开会议时，不会通知已加入会议的用户。
    
     打开会议进入和 **退出** 通知时，可以选择以下选项：
    
   - **姓名或电话号码** 当用户拨入会议时，当他们加入会议时，将播放其电话号码。
    
   - **音调** 当用户拨入会议时，当他们加入会议时，将播放音频音。
      
   - **要求呼叫者在加入会议之前录制其姓名** 如果关闭此功能，呼叫者在加入会议之前不会要求他们录制其姓名。

4. 若要设置会议的 PIN 长度，请在 PIN 长度列表中选择 PIN **的位数** 。

5. 若要指定是否向用户发送电子邮件，请启用或禁用如果用户的音频会议配置发生更改 **时自动发送电子邮件**。
    有关详细信息 [，请参阅](emails-sent-to-users-when-their-settings-change-in-teams.md) 当用户的音频会议设置在 Microsoft Teams 中更改时自动发送给用户的电子邮件，或当用户在 [Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) 中的设置更改时发送给用户的电子邮件。
 
6. 单击“**保存**”。 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 若要节省时间或自动执行此过程，可以使用 [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet。
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 借助 Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365，当您有多个任务需要执行时，可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell与仅使用 Microsoft 365 管理中心相比，在速度、简单性和工作效率方面具有许多优势，例如，一次为许多用户进行设置更改时。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[设置 Microsoft Teams 的音频会议](set-up-audio-conferencing-in-teams.md)

[为 Skype for Business Online 设置音频会议](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
