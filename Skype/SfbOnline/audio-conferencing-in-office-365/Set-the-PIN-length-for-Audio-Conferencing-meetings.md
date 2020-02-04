---
title: 在 Skype for Business Online 中设置音频会议的 PIN 长度
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: 了解 PIN 的长度和要求的参数，并参阅如何在 Skype for Business 中设置会议的长度。
ms.openlocfilehash: 9142c78c30c56702e2892d396b5688ee120cc83e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695807"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a>在 Skype for Business Online 中设置音频会议的 PIN 长度


> [!NOTE]
> 有关在 Microsoft Teams 中设置 PIN 长度的信息，请参阅[在 Microsoft Teams 中设置音频会议的 PIN 长度](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)。

When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers. The phone number you set will be included on the meeting invites for the Skype for Business app.
  
The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone. It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name. **Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers. Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>设置 PIN 长度
 
1. 在**Skype for business 管理中心**的左侧导航中，转到 "**音频会议** > **Microsoft 网桥设置**"。
    
2. 在 "**安全** > **PIN 长度**" 下，选择要用于 PIN 的数字位数，然后单击 "**保存**"。
    
> [!NOTE]
> [!注释] PIN 与会议 ID 不同。 会议 ID 由呼叫者在加入会议时使用。 它们用于标识会议。 PIN 用于对作为会议组织者的呼叫者进行身份验证。 

## <a name="want-to-know-more-about-pin-settings"></a>想要了解有关 PIN 设置的详细信息？

- PINs can be from 4 to 12 digits; the default is 5. Numbers are only used when creating PINs. Letters and special characters aren't used.
    
- A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting. If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.
    
- PIN 安全设置适用于与 Microsoft 网桥相关联的所有电话号码。它们将应用于使用与给定网桥相关联的电话号码的所有会议。 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet。
    
- 若要将 PIN 的数字位数设置为 8： `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你在一次为多个用户进行设置更改时。了解以下主题中的这些优势： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="see-also"></a>另请参阅

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
