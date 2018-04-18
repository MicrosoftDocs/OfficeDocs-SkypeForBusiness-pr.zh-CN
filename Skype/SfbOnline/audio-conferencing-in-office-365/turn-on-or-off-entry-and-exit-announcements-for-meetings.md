---
title: 打开或关闭会议的进入和退出通知
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. '
ms.openlocfilehash: a9c3788db6b5742b4f2b41961c3843b4939c315b
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a>打开或关闭会议的进入和退出通知

当您设置 Office 365 中的音频会议时，您将看到音频会议桥。 会议桥可以包含一个或多个用户将用来连接到业务或 Microsoft 小组会议 Skype 的电话号码。 
  
会议网桥负责应答使用电话拨入会议的用户的呼叫。 会议桥从会议自动助理应答带语音提示的调用方，然后，根据您的设置，可以播放通知，要求调用方来记录其姓名，并设置 PIN 安全性。 PIN 给 Skype 来业务或 Microsoft 小组会议组织者，并允许它们在无法启动时使用 Skype 业务或 Microsoft 小组应用程序为该会议启动会议。 但是，可以将它以便 PIN 不需要召开会议。
  
## <a name="setting-meeting-join-options"></a>设置会议加入选项

**使用 Microsoft 小组和 Skype 业务管理中心**

1. 在左侧的导航中，转到**会议** > **会议桥**。 

2. 在**会议桥**页的顶部，单击**桥接器设置**。 

3. **网桥的设置**窗格中启用或禁用**启用会议进入和退出通知以打开**。 默认情况下，此选项处于选中状态。 如果清除它，当有人进入或离开会议，不会通知用户已加入会议。
    
4. 在**入口/出口公告类型**，选择**名称或电话号码**或**色调**。
    
5. 启用或禁用**询问呼叫者记下其名称之前加入会议**。
    
6. 进行更改后，单击**应用**。

**使用 Skype 业务管理中心**
    
1. 在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 网桥的设置**。
    
2. 选中或清除**启用会议进入和退出通知以打开****会议连接体验**下。 默认情况下，此选项处于选中状态。 如果清除它，当有人进入或离开会议，不会通知用户已加入会议。
    
3. 在**入口/出口公告类型**，选择**名称或电话号码**或**色调**。
    
4. 选中或取消选中**询问呼叫者记下其名称之前加入会议**。
    
5. 完成更改后，单击" **保存**"。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet。
    
-  对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。 使用 Windows PowerShell，可以通过单点管理来管理 Office 365，这样做可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 许多相比具有的优势在速度、 简易性和生产率仅使用 Office 365 管理中心如当您所更改的设置对于许多用户一次。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[音频会议常见问题](audio-conferencing-common-questions.md)
