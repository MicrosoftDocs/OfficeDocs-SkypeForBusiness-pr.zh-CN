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
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: 更改音频会议网桥设置，包括进入和退出通知、播放名称或电话号码、音调和提示呼叫者记录其姓名。
ms.openlocfilehash: d9853826d9a93c5794017185f561b9d6a6cd1ffb
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641783"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>更改音频会议网桥的设置

在 Microsoft 365 或 Office 365 中设置音频会议时，你将从所谓的音频会议网桥接收用户的电话号码。 会议网桥可以包含一个或多个电话号码。 当呼叫者拨入会议时，将使用这些电话号码。 电话号码包含在 Teams 会议邀请的底部。
  
会议网桥会接听呼叫，并使用会议自动助理通过语音提示提示呼叫者，然后，根据你的设置，它可以播放通知，要求呼叫者记录其姓名，并控制 PIN 设置。 将 PIN 提供给会议组织者，让他们在不使用 Microsoft Teams 应用时开始会议。

  > [!IMPORTANT]
  > 仅当 Teams 应用用户尚未启动会议时，会议组织者才需要 PIN。 如果每个人都拨入会议，则会议组织者需要 PIN 才能开始会议。

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
    有关详细信息，请参阅 [Microsoft Teams 中音频会议设置更改时自动发送给用户的电子邮件](emails-sent-to-users-when-their-settings-change-in-teams.md) 。

6. 单击“**保存**”。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 若要节省时间或自动执行此过程，可以使用 [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) cmdlet。

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，可以使用单个管理点来管理 Microsoft 365 或 Office 365，以便在需要执行多个任务时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [为什么要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [使用 Windows PowerShell 管理 Microsoft 365 或Office 365的最佳方法](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell在速度、简单性和工作效率方面具有许多优势，而不是只使用Microsoft 365 管理中心，例如每次对许多用户进行设置更改时。 通过以下主题了解这些优势：

  - [Microsoft Teams PowerShell 概述](teams-powershell-overview.md)

  - [安装 Microsoft Teams PowerShell 模块](teams-powershell-install.md)
  
## <a name="related-topics"></a>相关主题

[设置 Microsoft Teams 的音频会议](set-up-audio-conferencing-in-teams.md)
