---
title: 打开或关闭条目和退出通知中 Skype 业务 online 的会议
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. '
ms.openlocfilehash: d6d1b70713ac0cd7a38f7de9cb84f0acb54cbe30
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490482"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>打开或关闭条目和退出通知中 Skype 业务 online 的会议

> [!Note]
> 进入和退出通知的 Microsoft 团队的有关信息，请参阅[打开或关闭参加和退出通知中的 Microsoft 团队会议](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)。

当您要设置 Office 365 中的音频会议时，您将看到音频会议桥。 会议桥可以包含一个或多个人员将用于连接到业务会议 Skype 的电话号码。 
  
会议网桥负责应答使用电话拨入会议的用户的呼叫。 会议桥应答来自会议自动助理的呼叫者使用语音提示并随后，具体取决于您的设置，可以播放通知，向呼叫者提出记录其姓名，并设置 PIN 安全。 PIN 赋予业务会议组织者，Skype 并允许它们如果它们无法启动会议的企业应用程序使用 Skype 开始会议。 但是，可以将它以便启动会议不需要 PIN。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>设置会议加入选项
    
1. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 网桥的设置**。
    
2. 在**会议的与会体验**中,，选中或清除**启用会议进入和退出通知，以打开**。 默认情况下，此选项处于选中状态。 如果清除它，某人进入或离开会议时，已加入会议的用户不会将收到通知。
    
3. 在**条目/退出通知类型**，选择**姓名或电话号码**或**提示音**。
    
4. 选中或取消选中**Ask 呼叫者在记录其姓名之前加入会议**。
    
5. 完成更改后，单击" **保存**"。
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet。
    
-  对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。使用 Windows PowerShell，可以通过单点管理来管理 Office 365，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么您需要使用 Office 365 PowerShell 中](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 已通过仅使用如时要进行设置更改多个用户一次在 Office 365 管理中心中快速、 简便起见和生产力很多好处。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[音频会议常见问题](audio-conferencing-common-questions.md)
