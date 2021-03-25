---
title: Skype for Business Online 中的设置更改时发送给用户的电子邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: '了解当 Skype for Business Online 中的电话拨入式会议设置更改时，将通过电子邮件自动向用户发送哪些信息。 '
ms.openlocfilehash: 4ab95af236fdb0ef8ff3aee6004fa8b11bf313af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110028"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>Skype for Business Online 中的设置更改时发送给用户的电子邮件

> [!Note]
> 如果要在 Microsoft Teams 中查找自动电子邮件信息，请参阅在 Microsoft Teams 中更改设置时 [发送给用户的电子邮件](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams)。

电子邮件将自动发送给使用 Microsoft 作为音频会议[](set-up-audio-conferencing.md)提供商启用音频会议的用户。
  
默认情况下，有四种类型的电子邮件将发送给启用了音频会议的用户。 但是，如果要限制向用户发送的电子邮件数，你可以将其关闭。 Microsoft 365 或 Office 365 中的音频会议将在以下时间向用户的电子邮件发送电子邮件：
  
- **音频会议许可证分配给他们，或者当你将音频会议提供商更改到 Microsoft 时。**
    
     此电子邮件包括会议 ID、会议的默认会议电话号码、用户的音频会议 PIN，以及使用 Skype for Business Online 会议更新工具（用于更新用户的现有会议）的说明和链接。 请参阅 [分配 Skype for Business 许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) 或将 Microsoft 分配为 [音频会议提供商](assign-microsoft-as-the-audio-conferencing-provider.md)。
    
    > [!NOTE]
    > [!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。 可以在组织中[设置音频会议动态 ID。](./reset-a-conference-id-for-a-user.md) 
  
    下面是此电子邮件的一个示例：
    
     ![Skype for Business 验证许可证](../images/audio-conferencing-user-enabled.png)
  
    你可以通过参阅 [Skype for Business 附加许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)了解有关 Skype for Business 许可的更多信息。
    
- **会议 ID 或用户默认会议电话号码更改。**
    
    此电子邮件包括会议 ID、默认会议电话号码以及使用 Skype for Business Online 会议更新工具为用户更新现有会议的说明和链接。 但是，此电子邮件不包括用户的音频会议 PIN。 请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。
    
    > [!NOTE]
    > [!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。 可以在组织中[设置音频会议动态 ID。](./reset-a-conference-id-for-a-user.md) 
  
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议信息已更改。](../images/audio-conferencing-info-change.png)
  
- **重置用户的音频会议 PIN。**
    
    此电子邮件包含组织者的音频会议 PIN、现有会议 ID 和用户的默认会议电话号码。 请参阅[重置音频会议 PIN。](reset-the-audio-conferencing-pin.md)
    
    > [!NOTE]
    > [!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。 可以在组织中[设置音频会议动态 ID。](./reset-a-conference-id-for-a-user.md) 
  
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议 PIN 已更改。](../images/audio-conferencing-pin-has-changed.png)
  
- **将删除用户的许可证，或者当音频会议提供商从 Microsoft 更改到其他提供商或"无"时。**
    
    从用户删除 **音频** 会议许可证时，或者将用户的音频会议提供商从 Microsoft 更改为第三方音频会议提供商或将提供商设置为"无"时，将 **发生这种情况。** 此电子邮件包含有关用户使用 Skype for Business Online 会议更新工具删除音频会议特定信息（例如默认会议电话号码或会议 ID）的说明和信息。
    
    请参阅 [为 Microsoft 365 商业版应用分配或删除许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。
    
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议已关闭。](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>更改发送给用户的电子邮件

您可以更改自动发送给用户的电子邮件，包括"来自联系人"显示名称 *中包含的电子邮件地址和* 电子邮件地址。 默认情况下，电子邮件的发件人来自 Microsoft 365 或 Office 365，但您可以使用 Windows PowerShell 和 [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet 更改电子邮件地址和 显示名称。 若要更改向用户发送电子邮件的电子邮件地址，必须：
  
- 在  _SendEmailFromAddress_ 参数中输入电子邮件地址。
    
- 在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。
    
- 将 _SendEmailOverride_ 参数设置为 _True。_
    
可以运行以下操作，更改发送给用户的电子邮件，例如电子邮件的发送显示名称电子邮件地址和电子邮件地址：
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  如果要更改电子邮件地址信息，需要确保环境的入站电子邮件策略允许来自地址中指定的自定义电子邮件。 如果决定覆盖" *来自* 联系人信息"，应验证电子邮件是否正确发送给用户。 为此，可以与组织中一个用户进行测试。
  
可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet 管理组织的其他设置，包括电子邮件。
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>如果不想向用户发送电子邮件，又该怎样做？

当禁用电子邮件发送给用户时，即使用户拥有分配的许可证，也不会向其发送电子邮件。 在这种情况下，会议 ID、默认会议电话号码以及更重要的是，其音频会议 PIN 不会发送给用户。 发生这种情况时，你必须通过向用户发送单独的电子邮件或呼叫他们进行通知。
  
默认情况下，电子邮件将发送给你的用户，但如果你想要阻止他们接收音频会议的电子邮件，可以使用 Skype for Business 管理中心或Windows PowerShell。 
 
![显示 Skype for Business 徽标的图标 ](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**  
    
1. 在 **Skype for Business 管理中心的** 左侧导航中，转到"**音频会议**  >  **""Microsoft 网桥设置"。**
    
2. 在 **"Microsoft 网桥设置"** 页面上，选择或清除"如果用户的音频会议设置更改，则自动 **向用户发送电子邮件"。** 
    
3. 单击“**保存**”。 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**使用Windows PowerShell**
  
1. 运行以下操作以禁用向你的用户发送所有电子邮件：
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet 管理组织的其他设置，包括电子邮件。
  
## <a name="what-else-should-you-know-about-this-email"></a>此电子邮件的其他须知事项。

- 有关如何启用和禁用自动向用户发送电子邮件的更多信息，请参阅[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-their-settings-change.md)。
    
- 有时用户会丢失其音频信息，你需要能够将其所有音频信息发送给他们。 为此，可以使用 Skype for Business 管理中心，然后单击用户的音频会议属性下的"通过电子邮件发送会议信息"。 请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。 但是，此信息不包括音频会议 PIN。
    
    下面是将发送给用户的电子邮件的一个示例：
    
     ![电话拨入式会议电子邮件](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 默认情况下，电子邮件的发件人来自 Microsoft 365 或 Office 365，但您可以使用 Windows PowerShell 和 [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet 更改电子邮件地址和 显示名称。
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365，当您有多个任务需要执行时，可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为何需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell比仅使用 Microsoft 365 管理中心具有许多速度、简单性和工作效率优势，例如，一次对多个用户进行设置更改时。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)