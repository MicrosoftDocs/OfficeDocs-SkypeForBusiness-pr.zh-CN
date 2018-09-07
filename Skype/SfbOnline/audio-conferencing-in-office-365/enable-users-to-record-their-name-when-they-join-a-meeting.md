---
title: 允许用户在 Skype for Business Online 中加入会议时记录其姓名
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
description: 了解如何启用或禁用用户在 Skype for Business Online 中加入会议时是否可以记录其姓名。
ms.openlocfilehash: 6022d7ebf0e653bc43373cb00faabc207f91562a
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850038"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>允许用户在 Skype for Business Online 中加入会议时记录其姓名

> [!Note]
> 如果您希望允许用户在 Teams 中记录他们的姓名，请参阅[  允许用户在加入 Microsoft Teams 中的会议时记录他们的姓名](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams) 。

在 Office 365 中设置音频会议时，您将收到电话号码和音频会议网桥。 会议网桥可以包含一个或多个电话号码，这些号码可以是专用或共享电话号码。
  
会议网桥负责应答使用电话拨入会议的用户的呼叫。 会议网桥通过来自自动助理的语音提示应答呼叫者，根据它们的具体设置，会议网桥可以播放通知、让呼叫者在录音中留下姓名以及为会议组织者设置 PIN 安全码。 会员组织者可以获得 PIN 码，以便他们启动会议。 然而，您也可以将其设置为无需 PIN 即可启动会议。

## <a name="set-whether-callers-should-record-their-name"></a>设置呼叫者是否应录制其姓名
    
1. 在 **Skype for Business 管理中心**中的左侧导航中，转到 **音频会议** > **Microsoft 桥接设置**。
    
2. 在 **会议的与会体验**中，请参阅标记为**打开启用会议加入和退出通知**的复选框。
    
  - **选中** 要求呼叫者在进入会议之前记录其姓名。 默认情况下，此选项处于选中状态。
    
  - **未选中** 不要求呼叫者在进入会议之前记录其姓名。
    
3. 完成更改后，单击 **保存**。
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet。
    
-  Windows PowerShell 的功能是管理用户以及允许用户执行的操作。 使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 与仅使用 Office 365 管理中心相比，Windows PowerShell 在速度、简化和工作效率方面具有许多优点，例如，当一次更改许多用户的设置时。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
