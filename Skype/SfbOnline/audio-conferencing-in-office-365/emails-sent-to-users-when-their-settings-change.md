---
title: 在 Skype for Business Online 中其设置发生更改时发送给用户的电子邮件
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
description: '了解当 Skype for business Online 中的电话拨入式会议设置更改时，通过电子邮件自动向用户发送哪些信息。 '
ms.openlocfilehash: e2f58bfe582b7adc6672c06bec0e90571ff9a96a
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164271"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>在 Skype for Business Online 中其设置发生更改时发送给用户的电子邮件

> [!Note]
> 如果要查找 Microsoft 团队中的自动电子邮件信息，请参阅在[Microsoft 团队中的设置更改时发送给用户的电子邮件](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams)。

电子邮件将自动发送给已使用 Microsoft 作为音频会议提供商[的音频会议的](set-up-audio-conferencing.md)用户。
  
默认情况下，将向已启用音频会议的用户发送四种类型的电子邮件。 但是，如果要限制向用户发送的电子邮件数，你可以将其关闭。 在以下情况中，Microsoft 365 或 Office 365 中的音频会议将向用户的电子邮件发送电子邮件：
  
- **向 Microsoft 分配音频会议许可证或将音频会议提供商更改为 Microsoft 时。**
    
     此电子邮件包括会议 ID、会议的默认会议电话号码、用户的音频会议 PIN 以及使用 Skype for Business Online 会议更新工具的说明和链接，用于更新用户的现有会议。 请参阅[分配 Skype for business 许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)或[指定 Microsoft 作为音频会议提供商](assign-microsoft-as-the-audio-conferencing-provider.md)。
    
    > [!NOTE]
    > [!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。 您可以[在您的组织中设置音频会议动态 id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。 
  
    下面是此电子邮件的一个示例：
    
     ![Skype for Business 验证许可证](../images/audio-conferencing-user-enabled.png)
  
    你可以通过参阅 [Skype for Business 附加许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)了解有关 Skype for Business 许可的更多信息。
    
- **会议 ID 或用户默认会议电话号码更改。**
    
    此电子邮件包括会议 ID、默认会议电话号码以及使用 Skype for Business Online 会议更新工具为用户更新现有会议的说明和链接。 但此电子邮件不包含用户的音频会议 PIN。 请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。
    
    > [!NOTE]
    > [!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。 您可以[在您的组织中设置音频会议动态 id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。 
  
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议信息已更改。](../images/audio-conferencing-info-change.png)
  
- **用户的音频会议 PIN 将重置。**
    
    此电子邮件包含组织者的音频会议 PIN、现有会议 ID 和用户的默认会议电话号码。 请参阅[重置音频会议 PIN 码](reset-the-audio-conferencing-pin.md)。
    
    > [!NOTE]
    > [!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。 您可以[在您的组织中设置音频会议动态 id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。 
  
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议 PIN 已更改。](../images/audio-conferencing-pin-has-changed.png)
  
- **当音频会议提供商从 Microsoft 更改为其他提供商或 "无" 时，将删除用户许可证。**
    
    如果从用户删除**音频会议**许可证或将用户的音频会议提供商从 Microsoft 更改为第三方音频会议提供商或将提供商设置为 "**无**"，则会出现此情况。 此电子邮件包含用户使用 Skype for Business Online 会议更新工具删除音频会议特定信息（如默认会议电话号码或会议 ID）的说明和信息。
    
    请参阅[分配或删除适用于企业的 Microsoft 365 应用的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。
    
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议已关闭。](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>更改发送给用户的电子邮件

您可以对自动发送给用户的电子邮件进行更改，包括 "*发件*人联系人" 信息中包含的电子邮件地址和显示名称。 默认情况下，电子邮件的发件人将来自 Microsoft 365 或 Office 365，但你可以使用 Windows PowerShell 和[set-csonlinedialinconferencingtenantsettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 更改电子邮件地址和显示名称。 若要对向用户发送电子邮件的电子邮件地址进行更改，必须执行以下操作：
  
- 在  _SendEmailFromAddress_ 参数中输入电子邮件地址。
    
- 在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。
    
- 将_SendEmailOverride_参数设置为_True_。
    
您可以通过运行以下内容来更改发送给用户的电子邮件，例如电子邮件的发件人电子邮件地址和电子邮件的显示名称：
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  如果要更改电子邮件地址信息，你需要确保你的环境的入站电子邮件策略允许来自自定义指定发件人地址的电子邮件。 如果您决定覆盖 "*发件*联系人" 信息，应验证电子邮件是否已正确发送给用户。 你可以通过在你的组织中的一个用户进行测试来执行此操作。
  
你可以使用[set-csonlinedialinconferencingtenantsettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 管理你的组织的其他设置，包括电子邮件。
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>如果不想向用户发送电子邮件，又该怎样做？

当禁用电子邮件发送给用户时，即使用户拥有分配的许可证，也不会向其发送电子邮件。 在此情况下，会议 ID、默认会议电话号码和更重要的是，其音频会议 PIN 不会发送给用户。 发生这种情况时，你必须通过向用户发送单独的电子邮件或呼叫他们进行通知。
  
默认情况下，将向你的用户发送电子邮件，但如果你希望阻止他们接收用于音频会议的电子邮件，则可以使用 Skype for Business 管理中心或 Windows PowerShell。 
 
![](../images/sfb-logo-30x30.png)**使用 skype for business 管理中心**显示 skype for business 徽标的图标  
    
1. 在**Skype for business 管理中心**的左侧导航中，转到 "**音频会议** > **Microsoft 网桥设置**"。
    
2. 在 " **Microsoft 网桥设置**" 页面上，选择或清除 "**如果其音频会议设置发生更改，则自动向用户发送电子邮件**"。 
    
3. 单击“**保存**”。 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**使用 Windows PowerShell**
  
1. 运行以下操作以禁用向你的用户发送所有电子邮件：
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

你可以使用[set-csonlinedialinconferencingtenantsettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 管理你的组织的其他设置，包括电子邮件。
  
## <a name="what-else-should-you-know-about-this-email"></a>此电子邮件的其他须知事项。

- 有关如何启用和禁用自动向用户发送电子邮件的更多信息，请参阅[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-their-settings-change.md)。
    
- 有时，用户会丢失其音频信息，您需要能够将他们的所有音频信息发送给他们。 你可以通过使用 Skype for Business 管理中心，然后单击用户的音频会议属性下的 "**通过电子邮件发送会议信息**" 来执行此操作。 请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。 但是，此信息不包括音频会议 PIN 码。
    
    下面是将发送给用户的电子邮件的一个示例：
    
     ![电话拨入式会议电子邮件](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 默认情况下，电子邮件的发件人将来自 Microsoft 365 或 Office 365，但你可以使用 Windows PowerShell 和[set-csonlinedialinconferencingtenantsettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 更改电子邮件地址和显示名称。
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，你可以使用单一的管理点管理 Microsoft 365 或 Office 365，这可以在你有多个任务时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么需要使用 Microsoft 365 或 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [通过 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你为多个用户同时进行设置更改时。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)
