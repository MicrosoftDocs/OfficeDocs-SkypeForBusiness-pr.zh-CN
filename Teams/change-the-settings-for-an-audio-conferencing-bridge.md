---
title: 更改音频会议网桥的设置
ms.author: heidip
author: MicrosoftHeidi
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
description: 更改音频会议网桥设置，包括进入和退出通知、播放名称或电话号码、音调和提示呼叫者记录其姓名。
ms.openlocfilehash: 48925c30d9ac42c76b6f00d8416d767c6e0ab14d
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823041"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>更改音频会议网桥的设置

在Microsoft 365或Office 365中设置音频会议时，将从所谓的音频会议网桥接收用户的电话号码。 会议网桥可以包含一个或多个电话号码。 当呼叫者拨入会议时，将使用这些电话号码。 电话号码包含在Skype for Business或Microsoft Teams会议邀请的底部。
  
会议网桥使用会议自动助理接听呼叫并提示呼叫者使用语音提示，然后，根据你的设置，它可以播放通知，要求呼叫者记录其姓名，并控制 PIN 设置。 将 PIN 提供给会议组织者，以便他们在不使用Skype for Business或Microsoft Teams应用时启动会议。

  > [!IMPORTANT]
  > 仅当Skype for Business或Microsoft Teams应用用户尚未启动会议时，会议组织者才需要 PIN。 如果每个人都拨入会议，则会议组织者需要 PIN 才能开始会议。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在左侧导航栏中，转到 **会议** > **会议网桥**。

2. 在 **“会议桥** ”页的顶部，单击 **“桥”设置**。

3. 在“ **桥设置”** 窗格中，选择：
   - **会议进入和退出通知** 如果关闭此功能，则在某人进入或离开会议时，不会通知已加入会议的用户。

     打开 **会议进入和退出通知** 时，可以选择以下选项：

   - **姓名或电话号码** 当用户拨入会议时，他们的电话号码将在加入会议时播放。

   - **色调** 当用户拨入会议时，加入会议时将播放音频音调。

   - **要求呼叫者在加入会议之前记录其姓名** 如果关闭此功能，则不会要求呼叫者在加入会议之前记录其姓名。

4. 若要设置会议的 PIN 长度，请在 **PIN 长度** 列表中选择 PIN 所需的数字数。

5. 若要指定是向用户发送电子邮件，请在 **用户的音频会议配置更改时启用或禁用自动向用户发送电子邮件**。
    有关详细信息，请参阅当[用户音频会议设置更改时自动发送给用户的电子邮件Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md)或发送[给用户的电子邮件（当其设置在 Skype for Business Online 中更改时）](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)。

6. 单击“**保存**”。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 若要节省时间或自动执行此过程，可以使用 [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) cmdlet。

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，可以使用单个管理点来管理Microsoft 365或Office 365，以便在需要执行多个任务时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [为什么要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [使用Windows PowerShell管理Microsoft 365或Office 365的最佳方法](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell在速度、简单性和工作效率方面具有许多优势，而不是只使用Microsoft 365 管理中心，例如每次对许多用户进行设置更改时。 通过以下主题了解这些优势：

  - [Windows PowerShell 和 Skype for Business Online 简介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [使用 Windows PowerShell 管理 Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)下载。
  
## <a name="related-topics"></a>相关主题

[设置 Microsoft Teams 的音频会议](set-up-audio-conferencing-in-teams.md)

[为联机Skype for Business设置音频会议](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
