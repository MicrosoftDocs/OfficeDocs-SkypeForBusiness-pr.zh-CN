---
title: 联机置 for Business 的音频会议中 Skype 的 PIN
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: '了解关于 Pin 应知道什么以及如何中重置它们 Skype 业务 online。 '
ms.openlocfilehash: 257f59f59d4fc86c91aa5496fe3db42573269065
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229248"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>联机置 for Business 的音频会议中 Skype 的 PIN

> [!Note]
> 有关重置 Microsoft 团队中的音频会议 Pin 的信息，请参阅[重置 Microsoft 团队中的音频会议 PIN](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)。

PIN 是为每个 Skype 业务启用音频会议的用户创建的数字组成的代码。 音频会议 Pin 使用会议组织者标识它们是会议组织者，并允许通过电话开始会议。 如果这些用户使用企业应用程序的 Skype 开始会议，不需要 PIN。 如果用户忘记了其 PIN，他们不能在他们已启用音频会议时发送给他们的电子邮件中找到它，管理员可以重置其 PIN，或者他们可以重置其自己的 PIN。
  
身份验证的用户加入企业应用程序或时组织者加入与他/她 PIN 通过电话使用 Skype 时，可以启动会议。 如果会议要求提供 PIN 才能启动，则通过电话加入会议的所有用户都将进入会议厅并将收听保持音乐，直至会议启动。 如果会议组织者不需要 PIN 来通过电话启动会议，则当呼叫者加入会议时，系统不会要求他们提供 PIN。
  
## <a name="reset-a-users-pin"></a>重置用户的 PIN

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到**Office 365 管理中心** > **for Business 的 Skype**，在左侧导航窗格中，单击**要进行音频会议**。
    
3. 单击**用户**，选择您要重置 PIN 的用户。
    
4. 在操作窗格中，在**PIN**下单击**重置**。
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>具有重置其自己的 PIN 的用户

通过使用**电话拨入式会议**页面上的**重置 PIN**选项，用户可以重置 PIN。 此页可访问三种方式之一：

* 在浏览器中，转到[https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling)。
* 在 for Business 的 Skype，单击**选项**，旁边的**显示菜单**箭头，然后单击**工具** > **电话拨入式会议设置**。
* 在 for Business 的 Skype，单击**选项**，单击在左侧的菜单中，**呼叫转接**，，然后在**多呼叫设置**部分中，单击**编辑设置联机**。 

## <a name="what-else-should-you-know-about-pins"></a>你还应该知道有关 PIN 的哪些信息？

- 出于安全考虑，PIN 仅在重置时向管理员显示一次。 由管理员重置 PIN 后，将作为列出 PIN *****业务管理中心的 Skype**和中在 Windows PowerShell 中使用 Get-CsCsOnlineDialInConfencingUser 时的结果。
    
- 默认情况下启用，自动向用户发送电子邮件，并且他们正在启用音频会议或时重置 PIN 时，用户将收到电子邮件与他们的 PIN。 但如果您已禁用自动发送电子邮件、 PIN 重置电子邮件将不会发送给用户，并且必须手动发送给用户的 PIN 信息。
    
- 当会议启动时，会议厅中的所有用户都将自动加入该会议。 例如，如果两个参与者在会议启动之前尝试加入会议，他们将进入会议厅并将收听保持音乐，当会议组织者通过电话使用 PIN 加入时，该会议将启动，会议厅中的参与者将加入会议。
    
- 默认设置是不允许由匿名呼叫者启动会议。
    
- 当您启用音频会议的用户时，默认情况下它们发送电子邮件，包括会议信息和其 PIN。 用户必须具有 Office 365 邮箱，因为一个新的 PIN 重置 PIN 时, 将发送到电子邮件到为用户设置其主 SMTP 地址 （别名） 中的用户。
    
- 当您设置了音频会议时，您设置所需的 Pin 在组织中的数字。 PIN 可以包含 4 至 12 个数字，默认情况下为 5 个。 如果您更改 PIN 长度设置，请设置仅应用于新生成的旋转中心点，并且不应用于启用了音频会议的现有用户的 PIN 设置。 请参阅[设置音频会议的 PIN 长度](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)。
    
- 默认情况下电子邮件将设置为用户的 Office 365 主 SMTP 地址。 您可以向 Office 365 的地址，例如 Hotmail 或 MSN 电子邮件地址发送电子邮件。 通过使用 Windows PowerShell，可以覆盖默认电子邮件地址。 如果用户在 Office 365 中没有 Exchange 邮箱，则此功能非常有用。
    
- 若要替代默认用户地址发送电子邮件的位置，租户管理员可以使用以下 cmdlet： 设置 CsOnlineDialInConferencingUser-amos.marble-ResetLeaderPIN-SendEmail-SendEmailToAddress"u@hotmail.com"。 SendEmail 参数需要替代的用户的电子邮件地址。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet。
    
- 你可以通过运行以下命令来设置 Amos Marble 的 PIN：
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。 请在以下主题中了解这些优点：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)
