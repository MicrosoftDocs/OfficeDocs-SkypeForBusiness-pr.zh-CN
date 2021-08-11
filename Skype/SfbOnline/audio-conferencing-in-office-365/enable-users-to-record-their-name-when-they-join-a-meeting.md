---
title: 允许用户在加入 Skype for Business Online 中的会议时录制其姓名
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
description: 了解如何启用或禁用用户是否可以在加入 Skype for Business Online 会议时录制其姓名。
ms.openlocfilehash: 53d57583004a143f78900b7e195084465f3344bc2617c4682709cf223a1860e9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335722"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>允许用户在加入 Skype for Business Online 中的会议时录制其姓名

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 如果您希望允许用户在 Teams 中记录他们的姓名，请参阅[  允许用户在加入 Microsoft Teams 中的会议时记录他们的姓名](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams) 。

当你在会议或会议Microsoft 365 Office 365时，你将收到电话号码以及所谓的音频会议网桥。 会议网桥可以包含一个或多个电话号码，这些号码可以是专用或共享电话号码。
  
会议网桥负责应答使用电话拨入会议的用户的呼叫。 会议网桥通过来自自动助理的语音提示来应答呼叫者，然后，根据他们的设置，可以播放通知、让呼叫者录制其姓名，以及为会议组织者设置 PIN 安全性。 PIN 被赋予会议组织者，以便他们启动会议。 然而，你也可以将其设置为无需 PIN 即可启动会议。

## <a name="set-whether-callers-should-record-their-name"></a>设置呼叫者是否应录制其姓名
    
1. 在 **Skype for Business管理** 中心的 左侧导航中，转到"**音频会议**  >  **Microsoft 网桥设置"。**
    
2. 在 **会议的与会体验** 中，请参阅标记为 **打开启用会议加入和退出通知** 的复选框。
    
   - **已选择** 呼叫者进入会议之前，将要求他们录制其姓名。 默认情况下，此选项处于选中状态。
    
   - **已清除** 呼叫者在进入会议之前不会要求他们录制其姓名。
    
3. 完成更改后，单击" **保存**"。
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet。
    
- Windows PowerShell管理用户以及允许用户执行哪些操作。 使用Windows PowerShell，可以使用Microsoft 365管理Office 365管理点，在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为何需要将 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell相比于仅使用 Microsoft 365 管理中心，在速度、简单性和工作效率方面具有许多优势，例如，一次对许多用户进行设置更改时。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[尝试或购买音频会议Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
