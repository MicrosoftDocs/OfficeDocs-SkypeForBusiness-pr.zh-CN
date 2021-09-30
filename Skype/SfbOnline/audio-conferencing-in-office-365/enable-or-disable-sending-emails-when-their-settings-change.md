---
title: Skype for Business Online 中的音频会议设置更改时启用或禁用发送电子邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: '了解 Skype 在 pin 或默认会议数等设置发生更改时如何启用或禁用向用户发送的电子邮件。 '
ms.openlocfilehash: 9deb04e418d00171375aec34ca873a89c8a31cdf
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011726"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Skype for Business Online 中的音频会议设置更改时启用或禁用发送电子邮件

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 如果您想要启用或禁用中的 Microsoft 团队发送电子邮件，请参阅 [Microsoft Teams 中的音频会议设置发生更改时启用或禁用发送电子邮件](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)。

要在 Microsoft Teams 中启用或禁用发送电子邮件，请参阅 Microsoft Teams 音频会议设置发生更改时启用或禁用发送电子邮件 但是，有时可能需要减少发送给用户的电子邮件Skype for Business数量。 在这种情况下，您可以禁用发送电子邮件。
  
如果禁用发送电子邮件，音频会议电子邮件不会发送给用户，包括为音频会议启用或禁用用户、重置其 PIN 的时间以及会议 ID 和默认会议电话号码更改时的电子邮件。
  
下面是为用户启用音频会议时发送给用户的电子邮件示例：
  
![音频会议电子邮件。](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>什么时候向用户发送电子邮件？

- 启用音频会议后，会向贵组织的用户发送多封电子邮件：
    
  - 向其分配 **音频会议** 许可证时。
    
  - 手动重置用户的音频会议 PIN 时。
    
  - 当你手动重置用户的会议 ID 时。
    
  - 删除其 **音频会议** 许可证时。
    
  - 当用户的音频会议提供商从 Microsoft 更改为其他提供商或"无 **"时**。
    
  - 当用户的音频会议提供商更改为 Microsoft 时。


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>启用或禁用向用户发送电子邮件

可以使用管理Skype for Business或Windows PowerShell来启用或禁用发送给用户的电子邮件。

 
![一个图标，显示Skype for Business徽标。](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**
    
1. 在 Skype for Business **管理中心的** 左侧导航中，单击"**音频会议"。**
    
2. 在 **Microsoft 网桥的设置** 页上，选中或清除 **自动向用户发送电子邮件，如果他们的音频会议设置更改**　。
    
3. 单击“**保存**”。
    
    > [!TIP]
    > 你也可以通过电子邮件向用户发送音频会议的设置， 方法是转到 **音频会议** > **用户**，选择用户，并单击 **通过电子邮件发送会议信息**。  如果这样做，将发送一封电子邮件，其中仅包括会议 ID 和会议电话号码，但不包括 PIN。  有关详细信息 [，请参阅向用户发送包含其音频会议信息](send-an-email-to-a-user-with-their-dial-in-information.md) 的电子邮件。
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**使用Windows PowerShell**
  
- 运行以下操作以禁用发送电子邮件： 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

     要获取此 cmdlet 的帮助，请参阅 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)。
    
## <a name="what-else-should-you-know"></a>你还需了解哪些信息？

- 禁用自动电子邮件后，仍可以使用会议管理中心手动触发Skype for Business会议 ID 和电话号码的电子邮件。 但是，如果这样做，不会包含 PIN。 如果要重置音频会议 PIN 并禁用发送电子邮件，则需要以其他方式将其发送给用户。
    
- 可以使用 Skype for Business 管理中心或 Windows PowerShell 禁用向用户发送电子邮件。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 可以使用这些 cmdlet 来节省时间或自动执行此操作。
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，Microsoft 365管理Office 365管理点，可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为何需要将 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell比仅使用 Microsoft 365 管理中心 具有许多速度、简单性和工作效率优势，例如，一次对许多用户进行设置更改时。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。 此模块仅在 64 位计算机上受支持，可从 Microsoft 下载中心下载并安装 Teams [PowerShell](https://go.microsoft.com/fwlink/?LinkId=294688)模块 (。/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md) 。
  
## <a name="related-topics"></a>相关主题

[当用户的音频会议设置更改时发送给用户的电子邮件](emails-sent-to-users-when-their-settings-change.md)

[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)
