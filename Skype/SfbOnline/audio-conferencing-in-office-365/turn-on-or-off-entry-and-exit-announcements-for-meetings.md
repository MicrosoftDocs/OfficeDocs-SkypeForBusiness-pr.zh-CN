---
title: 打开或关闭 Skype for Business Online 中的会议加入和退出公告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '了解如何使用 Skype for Business 管理中心打开或关闭 Skype for Business Online 会议的加入和退出公告。 '
ms.openlocfilehash: 50f2279f309e77126cc71e922b75afe1342b09863220e4c47c32581e6b85bcc9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326968"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>打开或关闭 Skype for Business Online 中的会议加入和退出公告

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 打开或关闭 Skype for Business Online 中的会议加入和退出公告[](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)

当你在会议或会议Microsoft 365音频Office 365，你将获得音频会议网桥。 会议桥可以包含一个或多个人员用于致电 Skype for Business 会议的电话号码。 
  
会议网桥负责应答使用电话拨入会议的用户的呼叫。 会议网桥通过来自会议自动助理的语音提示应答呼叫者，然后根据你的设置，可以播放通知、让呼叫者录制其姓名以及设置 PIN 安全。 为 Skype for Business 会议组织者提供了 PIN，这让他们能够在无法使用 Skype for Business 应用开始会议的情况下开始会议。 但你可以设置不需要使用 PIN 即可启动会议。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>设置会议加入选项
    
1. 在 **Skype for Business管理** 中心的 左侧导航中，转到"**音频会议**  >  **Microsoft 网桥设置"。**
    
2. 在 **"会议加入体验"** 下，选择或清除"启用会议进入和 **退出通知"以打开**。 默认情况下，此选项处于选中状态。 如果你将其取消选中，则当有人进入或离开会议时，已加入会议的用户不会收到通知。
    
3. 在 **进入/退出公告类型** 下，选择 **姓名或电话号码** 或 **提示音**。
    
4. 选中或取消选中 **"让呼叫者在加入会议之前录制其姓名"。**
    
5. 完成更改后，单击" **保存**"。
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet。
    
- 对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。 使用Windows PowerShell，可以使用Microsoft 365管理Office 365管理点，在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为何需要将 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell在速度、简单性和工作效率方面具有许多优点Microsoft 365 管理中心例如，当您一次为许多用户更改设置时。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[音频会议常见问题](/MicrosoftTeams/audio-conferencing-common-questions)
