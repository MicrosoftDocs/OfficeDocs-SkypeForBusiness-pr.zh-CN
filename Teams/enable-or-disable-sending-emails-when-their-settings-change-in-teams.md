---
title: 启用或禁用发送电子邮件中的 Microsoft 团队的音频会议设置更改时
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解如何启用或禁用 Skype 向用户设置 pin 如发生更改时或 Microsoft 团队中的默认会议号码更改发送电子邮件。 '
ms.openlocfilehash: 5d18d039c379bb56a861ba6f6a36d23f301150b4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861888"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>启用或禁用发送电子邮件中的 Microsoft 团队的音频会议设置更改时

他们启用音频会议时，将自动通过电子邮件通知用户。 有时可能，但是，当您想要减少发送给 Microsoft 团队用户的电子邮件数。 在这种情况下，您可以禁用发送电子邮件。
  
如果您禁用发送电子邮件，就不会音频会议电子邮件发送给用户，当用户处于启用或禁用音频会议以及会议 ID 和默认会议电话号码的更改时重置其 PIN，包括电子邮件.
  
下面是他们启用音频会议时，向用户发送的电子邮件的示例：
  
![音频会议电子邮件](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>什么时候向用户发送电子邮件？

- 有多个电子邮件发送给组织中的用户启用了后为音频会议：
    
  - 当**音频会议**许可证分配给它们。
    
  - 当您手动重置用户的音频会议 PIN。
    
  - 当你手动重置用户的会议 ID 时。
    
  - 当**音频会议**许可证已从它们。
    
  - 当用户的音频会议提供商从 Microsoft 更改为其他提供程序或**无**。
    
  - 向 Microsoft 更改时用户的音频会议提供商。


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>启用或禁用从发送给用户的电子邮件

您可以使用的 Microsoft 团队或 Windows PowerShell 启用或禁用电子邮件发送给用户。

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**
1. 在左侧导航窗格中，转到**会议** > **会议桥**。 

2. 在**会议桥**页的顶部，单击**网桥的设置**。 

3. 在**桥设置**窗格中，启用或禁用**自动发送电子邮件发送给用户，如果其电话拨入式设置更改**。

4. 单击" **保存**"。

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**使用 Windows PowerShell**
  
请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。

    
## <a name="want-to-know-more-about-windows-powershell"></a>要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。
    
  
## <a name="related-topics"></a>相关主题

[其音频会议设置更改时向用户发送的电子邮件](emails-sent-to-users-when-their-settings-change-in-teams.md)

[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


