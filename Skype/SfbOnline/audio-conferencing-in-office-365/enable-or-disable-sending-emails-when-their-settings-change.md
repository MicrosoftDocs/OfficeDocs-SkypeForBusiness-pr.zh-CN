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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解 Skype 在 pin 或默认会议数等设置发生更改时如何启用或禁用向用户发送的电子邮件。 '
ms.openlocfilehash: fc6a248974dba22c18cce00246b3b9312f294229
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883974"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Skype for Business Online 中的音频会议设置更改时启用或禁用发送电子邮件

> [!Note]
> 如果您想要启用或禁用中的 Microsoft 团队发送电子邮件，请参阅 [Microsoft Teams 中的音频会议设置发生更改时启用或禁用发送电子邮件](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)。

|||UNTRANSLATED_CONTENT_START|||Users are automatically notified by email when they are enabled for Audio Conferencing.|||UNTRANSLATED_CONTENT_END||| 有时可能，但是，当您想要减少的电子邮件发送到 Skype 业务用户的数量。 在这种情况下，您可以禁用发送电子邮件。
  
如果您禁用发送电子邮件，就不会音频会议电子邮件发送给用户，当用户处于启用或禁用音频会议以及会议 ID 和默认会议电话号码的更改时重置其 PIN，包括电子邮件.
  
下面是他们启用音频会议时，向用户发送的电子邮件的示例：
  
![音频会议电子邮件](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>什么时候向用户发送电子邮件？

- 有多个电子邮件发送给组织中的用户启用了后为音频会议：
    
  - 向其分配**音频会议**许可证时。
    
  - 当您手动重置用户的音频会议 PIN。
    
  - 当你手动重置用户的会议 ID 时。
    
  - 删除其**音频会议**许可证时。
    
  - 当用户的音频会议提供商从 Microsoft 更改为其他提供程序或**无**。
    
  - 向 Microsoft 更改时用户的音频会议提供商。


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>启用或禁用从发送给用户的电子邮件

您可以使用业务管理中心的 Skype 或 Windows PowerShell 启用或禁用电子邮件发送给用户。

 
![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**
    
1. 在**业务管理中心的 Skype**，在左侧导航窗格中，单击**音频会议**。
    
2. 在 **Microsoft 网桥的设置** 页上，选中或清除 **自动向用户发送电子邮件，如果他们的音频会议设置更改**　。
    
3. 单击" **保存**"。
    
    > [!TIP]
    > 你也可以通过电子邮件向用户发送音频会议的设置， 方法是转到**音频会议** > **用户**，选择用户，并单击 **通过电子邮件发送会议信息**。  如果执行此操作时，将仅包含会议 ID 和会议电话号码，但不是 PIN 发送电子邮件。  有关详细信息，请参阅[发送对其进行音频会议信息的用户电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**使用 Windows PowerShell**
  
- 运行以下命令以禁用发送电子邮件： 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

     要获取此 cmdlet 的帮助，请参阅 [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)。
    
## <a name="what-else-should-you-know"></a>你还需了解哪些信息？

- 禁用自动电子邮件后，您可以仍手动触发发送电子邮件与业务管理中心的使用 Skype 的会议 ID 和电话号码。 但是，如果执行此操作时，将不会包含 PIN。 如果您要重置 PIN 的音频会议和发送电子邮件被禁用，您需要向用户发送中另一种方法。
    
- 可以使用 Skype for Business 管理中心或 Windows PowerShell 禁用向用户发送电子邮件。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 可以使用这些 cmdlet 来节省时间或自动执行此操作。
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[其音频会议设置更改时向用户发送的电子邮件](emails-sent-to-users-when-their-settings-change.md)

[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)


