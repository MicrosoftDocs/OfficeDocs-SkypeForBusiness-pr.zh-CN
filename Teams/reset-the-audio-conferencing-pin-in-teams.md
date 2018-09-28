---
title: 在 Microsoft Teams 中重置音频会议 PIN
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解你应该了解的 PIN 相关信息以及如何在 Microsoft Teams 中重置 PIN。 '
ms.openlocfilehash: 292cc1c042816236fed35b536dd529b49e902203
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2018
ms.locfileid: "25347495"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>在 Microsoft Teams 中重置音频会议 PIN

PIN 是为每个启用音频会议的 Microsoft 团队用户创建的数字组成的代码。 音频会议 Pin 使用会议组织者标识它们是会议组织者，并允许通过电话开始会议。 如果他们使用的 Microsoft 团队应用程序启动会议，不需要 PIN。 如果用户忘记了其 PIN，他们不能在他们已启用音频会议时发送给他们的电子邮件中找到它，管理员可以重置其 PIN，或者他们可以重置其自己的 PIN。
  
经过身份验证的用户加入使用 Microsoft 团队应用程序或时组织者加入与他/她 PIN 通过电话时，可以开始会议。 如果会议要求提供 PIN 才能启动，则通过电话加入会议的所有用户都将进入会议厅并将收听保持音乐，直至会议启动。 如果会议组织者不需要 PIN 来通过电话启动会议，则当呼叫者加入会议时，系统不会要求他们提供 PIN。

## <a name="reset-a-users-pin"></a>重置用户的 PIN

![团队-徽标-30x30.png](media/teams-logo-30x30.png) 使用 Microsoft 团队和 Skype for Business Admin Center

1. 在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。

2. 单击**编辑**。

3. 在**音频会议**，下单击**重置 PIN**。

4. 单击**重置**。
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>具有重置其自己的 PIN 的用户

1. 让用户转到[https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing)。
2. 单击**重置 PIN**。 


## <a name="what-else-should-you-know-about-pins"></a>你还应该知道有关 PIN 的哪些信息？

- 出于安全考虑，PIN 仅在重置时向管理员显示一次。 由管理员重置 PIN 后，将作为列出 PIN ***。
    
- 默认情况下启用，自动向用户发送电子邮件，并且他们正在启用音频会议或时重置 PIN 时，用户将收到电子邮件与他们的 PIN。 但如果您已禁用自动发送电子邮件、 PIN 重置电子邮件将不会发送给用户，并且必须手动发送给用户的 PIN 信息。
    
- 当会议启动时，会议厅中的所有用户都将自动加入该会议。 例如，如果两个参与者在会议启动之前尝试加入会议，他们将进入会议厅并将收听保持音乐，当会议组织者通过电话使用 PIN 加入时，该会议将启动，会议厅中的参与者将加入会议。
    
- 默认设置是不允许由匿名呼叫者启动会议。
    
- 当您启用音频会议的用户时，默认情况下它们发送电子邮件，包括会议信息和其 PIN。 用户必须具有 Office 365 邮箱，因为一个新的 PIN 重置 PIN 时, 将发送到电子邮件到为用户设置其主 SMTP 地址 （别名） 中的用户。
    
- 当您设置了音频会议时，您设置所需的 Pin 在组织中的数字。 PIN 可以包含 4 至 12 个数字，默认情况下为 5 个。 如果您更改 PIN 长度设置，请设置仅应用于新生成的旋转中心点，并且不应用于启用了音频会议的现有用户的 PIN 设置。 请参阅[设置音频会议的 PIN 长度](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。
    
- 默认情况下电子邮件将设置为用户的 Office 365 主 SMTP 地址。 您可以向 Office 365 的地址，例如 Hotmail 或 MSN 电子邮件地址发送电子邮件。 通过使用 Windows PowerShell，可以覆盖默认电子邮件地址。 如果用户在 Office 365 中没有 Exchange 邮箱，则此功能非常有用。

    

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。
  
## <a name="related-topics"></a>相关主题

[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)
