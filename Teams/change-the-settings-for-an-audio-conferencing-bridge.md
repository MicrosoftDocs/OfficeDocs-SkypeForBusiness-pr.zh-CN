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
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.audioconferencing.bridgesettings
ms.custom:
- Audio Conferencing
description: '获取所需更改用于提示呼叫者和它们不使用 Skype 业务或 Microsoft 团队的应用程序时收集名称和 pin 的会议组织者的会议桥的设置的步骤。 '
ms.openlocfilehash: 04ad6cfe3de9b4549db6382fe790b7fb8c644fc7
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494194"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>更改音频会议网桥的设置

要设置 Office 365 中的音频会议，您会收到的电话号码为用户从所谓音频会议桥。 会议网桥可以包含一个或多个电话号码。 呼叫者拨入会议时，将使用这些电话号码。 包含业务或 Microsoft 团队的会议邀请的 Skype 底部的电话号码。
  
会议桥接听电话，并提示呼叫者使用语音提示使用会议自动助理，然后，具体取决于您的设置，可播放通知、 提出呼叫者在记录其姓名，然后控制 PIN 设置。 旋转中心点授予对会议组织者允许其开始会议时不使用 Skype 业务或 Microsoft 团队的应用程序。

  > [!IMPORTANT]
  > PIN 才所需的会议组织者时为业务或 Microsoft 团队的应用程序用户 Skype 不起作用已经启动会议。 所有人都拨入会议，PIN 需要会议组织者要开始会议。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![团队-徽标-30x30.png](media/teams-logo-30x30.png) 使用 Microsoft 团队管理中心

1. 在左侧导航窗格中，转到**会议** > **会议桥**。 

2. 在**会议桥**页的顶部，单击**网桥的设置**。 

3. 在**桥设置**窗格中，选择： 
   - **会议条目和退出通知**如果您关闭此操作，在某人进入或离开会议时，不会通知已加入会议的用户。
    
     当您打开**会议进入和退出通知**时，您可以选择以下选项：
    
   - **姓名或电话号码**当用户拨入会议时，当用户加入它时将播放其电话号码。
    
   - **音**当用户拨入会议时，当用户加入它时将播放音频音。
      
   - **Ask 呼叫者在记录其姓名之前加入会议**如果您关闭此操作，呼叫者不需要记录其姓名，他们加入会议之前。

4. 若要设置会议的 PIN 长度，选择您希望在**PIN 长度**列表的 PIN 的位数。

5. 若要指定是否向用户发送电子邮件，启用或禁用**自动发送电子邮件发送给用户，如果其音频会议配置更改**。
    有关详细信息，请参阅[电子邮件自动发送给用户的 Microsoft 团队中更改其音频会议设置时](emails-sent-to-users-when-their-settings-change-in-teams.md)或[电子邮件发送给用户时其设置业务 online Skype 中发生更改](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)。
 
6. 单击“**保存**”。 


## <a name="sfb-logo-30x30pngmediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![sfb-logo-30x30.png](media/sfb-logo-30x30.png)  使用 Skype for Business 管理中心

 **呼叫者加入会议时设置的会议体验**
    
1. 在**Skype 业务管理中心的**中，在左侧导航中转到**音频会议** > **Microsoft 网桥的设置**。
    
2. 在**Microsoft 桥设置**页上，在**会议加入体验**，下选择：
    
   - " **启用会议进入和退出通知**"此选项默认情况下选中。 如果清除该复选框，某人进入或离开会议时，已加入会议的用户不会收到通知。
    
   - 当选择了**启用会议进入和退出通知，以打开**时，您可以从**项/退出通知类型**列表选择这些选项：
    
   - **姓名或电话号码**当用户拨入会议时，当用户加入它时将播放其电话号码。
    
   - **音**当用户拨入会议时，当用户加入它时将播放音频音。
  
   - " **要求呼叫者在加入会议之前录制其名称**"此选项默认情况下选中。 如果清除该复选框，呼叫者不需要记录其姓名，他们加入会议之前。
    
3. 完成更改后，单击" **保存**"。
    
**设置会议的 PIN 长度**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 网桥的设置**。
    
4. 在**Microsoft 网桥的设置**页上的在**安全**下，输入您希望在**PIN 长度**列表中，PIN 的位数，然后单击**保存**。
    
    > [!IMPORTANT]
    > PIN 必须介于4到12位之间。 
  
**选择是否向用户发送电子邮件**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 网桥的设置**。
    
4. 在**Microsoft 网桥的设置**页上，选择或清除**其电话拨入式信息改变时自动发送给用户的电子邮件**，，然后单击**保存**。
    
    有关详细信息，请参阅[电子邮件自动发送给用户的 Microsoft 团队中更改其音频会议设置时](emails-sent-to-users-when-their-settings-change-in-teams.md)或[电子邮件发送给用户时其设置业务 online Skype 中发生更改](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 要保存时间或自动执行此过程，您可以使用[集 CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet。
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[设置音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
