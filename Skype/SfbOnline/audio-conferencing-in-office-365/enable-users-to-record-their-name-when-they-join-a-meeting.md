---
title: 允许用户在 Skype for Business Online 中加入会议时记录其名称
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 了解如何启用或禁用当用户在 Skype for Business Online 中加入会议时是否可以记录他们的姓名。
ms.openlocfilehash: d6bb98c2d3c6b12479aea4fbdfdc717491c9893e
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164151"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>允许用户在 Skype for Business Online 中加入会议时记录其名称

> [!Note]
> 如果您希望允许用户在 Teams 中记录他们的姓名，请参阅[  允许用户在加入 Microsoft Teams 中的会议时记录他们的姓名](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams) 。

当您在 Microsoft 365 或 Office 365 中设置音频会议时，您将收到电话号码和 "音频会议桥"。会议桥可以包含一个或多个电话号码，这些电话号码可以是专用电话号码或共享电话号码。
  
The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.

## <a name="set-whether-callers-should-record-their-name"></a>设置呼叫者是否应录制其姓名
    
1. 在**Skype for business 管理中心**的左侧导航中，转到 "**音频会议** > **Microsoft 网桥设置**"。
    
2. 在 **会议的与会体验**中，请参阅标记为**打开启用会议加入和退出通知**的复选框。
    
   - **Selected** Callers will be asked to record their name before they enter the meeting. This is selected by default.
    
   - 已**清除**在进入会议之前，不会要求呼叫者录制其姓名。
    
3. 完成更改后，单击" **保存**"。
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet。
    
- Windows PowerShell 全部用于管理用户以及允许用户执行的操作。使用 Windows PowerShell，你可以使用单一的管理点管理 Microsoft 365 或 Office 365，这可以在你有多个任务时简化日常工作。若要开始使用 Windows PowerShell，请参阅以下主题：
    
  - [为什么需要使用 Microsoft 365 或 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [通过 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你为多个用户同时进行设置更改时。了解以下主题中的这些优势： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[在 Microsoft 365 或 Office 365 中试用或购买音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
