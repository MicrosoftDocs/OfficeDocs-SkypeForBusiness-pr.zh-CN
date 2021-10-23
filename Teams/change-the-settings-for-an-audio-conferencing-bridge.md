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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: 更改音频会议网桥设置，包括进入和退出通知、播放姓名或电话号码、音调，以及提示呼叫者录制其姓名。
ms.openlocfilehash: 0c64fa8c8717ae7fd401c4476896e6e52e833769
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537043"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>更改音频会议网桥的设置

当你在会议或会议Microsoft 365 Office 365，你将收到来自音频会议网桥的用户的电话号码。 会议网桥可以包含一个或多个电话号码。 呼叫者拨入会议时，将使用这些电话号码。 电话号码包含在会议邀请或会议Skype for Business Microsoft Teams底部。
  
会议网桥应答呼叫，然后使用会议自动助理通过语音提示提示呼叫者，然后根据你的设置，它可以播放通知、让呼叫者录制其姓名并控制 PIN 设置。 PIN 被赋予给会议组织者，以便他们在没有使用应用或Skype for Business时Microsoft Teams会议。

  > [!IMPORTANT]
  > 只有当会议组织者尚未启动会议Skype for Business Microsoft Teams用户才需要 PIN。 如果每个人都拨入会议，会议组织者需要 PIN 才能启动会议。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

##  <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在左侧导航栏中，转到"**会议**  >  **会议网桥"。** 

2. 在"会议网桥"**页面顶部**，单击"**网桥设置"。** 

3. 在" **桥设置"** 窗格中，选择： 
   - **会议进入和退出通知** 如果关闭此功能，则当某人进入或离开会议时，已加入会议的用户不会收到通知。
    
     打开"会议进入和 **退出通知"** 时，可以选择以下选项：
    
   - **姓名或电话号码** 当用户拨入会议时，当他们加入会议时，将播放其电话号码。
    
   - **音调** 当用户拨入会议时，当他们加入会议时将播放音频音。
      
   - **要求呼叫者在加入会议之前录制其姓名** 如果关闭此功能，呼叫者在加入会议之前不会要求他们录制其姓名。

4. 若要设置会议的 PIN 长度，请在"PIN 长度"列表中选择 PIN **的位数** 。

5. 若要指定是否向用户发送电子邮件，请启用或禁用"如果用户的音频会议配置发生更改时自动 **向用户发送电子邮件"。**
    有关详细信息[，请参阅](emails-sent-to-users-when-their-settings-change-in-teams.md)当用户的音频会议设置在 Microsoft Teams 中更改时自动发送给用户的电子邮件，或当用户在[Skype for Business Online 中设置更改时发送给](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)用户的电子邮件。
 
6. 单击“**保存**”。 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 若要节省时间或自动执行此过程，可以使用 [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) cmdlet。
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，可以使用Microsoft 365管理Office 365管理点来管理任务或任务，当您有多个任务需要执行时，可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell比仅使用 Microsoft 365 管理中心 在速度、简单性和工作效率方面具有许多优势，例如，一次对许多用户进行设置更改时。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[设置 Microsoft Teams 的音频会议](set-up-audio-conferencing-in-teams.md)

[为 Skype for Business Online 设置音频会议](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)