---
title: 通过电话在 Skype for Business Online 开始音频会议而无 PIN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '了解如何启用或禁用从 Skype for Business Online 管理中心或使用 PowerShell 脚本参加会议的匿名呼叫者。 '
ms.openlocfilehash: 5403d984d5e87b929db4d1ebc3c7eeba34f3744c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58600857"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>通过电话在 Skype for Business Online 开始音频会议而无 PIN

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 有关在 Microsoft Teams 无 PIN 启动音频会议的信息，请参阅[通过电话在 Microsoft Teams 中无 PIN 开始音频会议](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)。

拨入会议的用户可能很难在会议大厅中收听音乐，因为会议组织者Skype for Business会议。 
  
默认情况下，如果会议组织者呼叫呼叫会议，则启动会议需要 PIN。 您可以设置它，以便任何人都可以拨入会议，并且系统不会提示输入 PIN 以启动会议。 你可以使用 Skype for Business 管理中心为单个用户启用或禁用此设置。
  
如果有人从应用启动会议，会议组织者不需要SKYPE FOR BUSINESS PIN。 只有当会议组织者通过电话加入会议时，才需要 PIN。 为音频用户分配音频会议许可证并启用音频会议时，会议 PIN将发送给音频用户。 请参阅 [向用户发送](send-an-email-to-a-user-with-their-dial-in-information.md) 包含其音频会议信息的电子邮件，以及当用户的音频会议设置更改时 [自动发送给用户的电子邮件](emails-sent-to-users-when-their-settings-change.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>启用或禁用匿名呼叫者加入会议
    
1. 在 **Skype for Business管理** 中心的 左侧导航中，转到"**音频会议用户**  >  **"。** 
    
2. 在列表中选择用户，在"操作"窗格中单击"编辑 **"。** 
    
3. 在用户的属性页面上的"会议选项"下，选择或清除"允许未经身份验证的呼叫者成为 **会议的第一人"。如果没有，则他们将在大厅中等待，直到经过身份验证的用户加入**。
    
4. 单击“**保存**”。 


    
 **使用 Windows Powershell**
  
- 请运行以下命令： 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>你还需了解哪些信息？

- 如果要重置 PIN，请参阅[重置音频会议 PIN。](reset-the-audio-conferencing-pin.md)
    
- 如果禁用了匿名访问，或者不需要 PIN 来启动会议：
    
  - 如果会议尚未开始 (则会议中还没有人) ：呼叫者是组织者，则系统将会提示呼叫者;如果说"是"，系统会提示他输入 PIN，输入 PIN 后，会议将开始，用户将加入会议。
    
  - 如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。
    
- 如果启用了匿名访问，或者不需要 PIN 来启动会议：
    
  - 如果尚未启动会议（还没有会议）：如果呼叫者是组织者，将不会收到提示，并且从不提示她提供 PIN。 由于组织者的设置设置为"关"，会议将开始，匿名呼叫者将加入会议。
    
  - 如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或为多个用户自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet。
    
- 对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。 使用Windows PowerShell，Microsoft 365 Office 365单点管理来管理任务或任务，可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为何需要将 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell比仅使用 Microsoft 365 管理中心 具有许多速度、简单性和工作效率优势，例如，一次为许多用户更改设置时。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[尝试或购买音频会议Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
