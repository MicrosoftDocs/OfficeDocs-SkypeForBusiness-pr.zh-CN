---
title: 音频会议设置更改时Email选项
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '了解如何在 Teams 中设置（如固定更改或默认会议编号更改）时启用或禁用 Microsoft Teams 向用户发送电子邮件。 '
ms.openlocfilehash: a5119d6f612ed083ac4e72ab52f6bb189af4c9d1
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642103"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>在 Microsoft Teams 中启用或禁用在音频会议设置更改时发送电子邮件

要在 Microsoft Teams 中启用或禁用发送电子邮件，请参阅 Microsoft Teams 音频会议设置发生更改时启用或禁用发送电子邮件 但是，有时可能需要减少发送给 Microsoft Teams 用户的电子邮件数。 在这种情况下，您可以禁用发送电子邮件。
  
如果禁用发送电子邮件，则不会向用户发送音频会议电子邮件，包括为音频会议启用或禁用用户、重置其 PIN 时以及会议 ID 和默认会议电话号码更改时的电子邮件。
  
下面是启用音频会议时发送给用户的电子邮件示例：
  
![音频会议电子邮件的示例。](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>什么时候向用户发送电子邮件？

- 有几封电子邮件在启用音频会议后发送给组织中的用户：

  - 向其分配 **音频会议** 许可证时。

  - 手动重置用户的音频会议 PIN 时。

  - 当你手动重置用户的会议 ID 时。

  - 删除其 **音频会议** 许可证时。

  - 当用户的音频会议提供商从 Microsoft 更改为另一个提供商或 **None** 时。

  - 当用户的音频会议提供程序更改为 Microsoft 时。

## <a name="enable-or-disable-email-from-being-sent-to-users"></a>启用或禁用发送给用户的电子邮件

可以使用 Microsoft Teams 或Windows PowerShell启用或禁用发送给用户的电子邮件。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。

2. 在 **“会议桥** ”页的顶部，单击 **“桥”设置**。

3. 在 **“桥”设置** 窗格 **中，如果用户的拨入设置发生更改，则启用或禁用自动向用户发送电子邮件**。

4. 单击“**保存**”。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>使用 Windows PowerShell

还可以使用 Microsoft Teams PowerShell 模块并运行：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) 管理组织的其他设置，包括电子邮件。

有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps) 。

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，可以使用单个管理点来管理 Microsoft 365 或 Office 365，以便在需要执行多个任务时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

- [为什么要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理 Office 365 的最佳方式](/previous-versions//dn568025(v=technet.10))

有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。

## <a name="related-topics"></a>相关主题

[当用户的音频会议设置更改时发送给用户的电子邮件](emails-sent-to-users-when-their-settings-change-in-teams.md)

[向用户发送包含其音频会议信息的电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
