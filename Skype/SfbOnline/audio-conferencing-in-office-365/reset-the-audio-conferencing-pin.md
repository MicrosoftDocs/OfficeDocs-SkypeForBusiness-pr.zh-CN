---
title: 在 Skype for Business Online 中重置音频会议 PIN
ms.author: tonysmit
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '了解你应该了解的关于 PIN 以及如何在 Skype for Business Online 中重置它们。 '
ms.openlocfilehash: 4b042775a5a0525099c0116d7d55d0092f560cdf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114198"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>在 Skype for Business Online 中重置音频会议 PIN

> [!Note]
> 有关在 Microsoft Teams 中重置音频会议 PIN 的信息，请参阅在 Microsoft Teams 中重置音频[会议 PIN。](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)

PIN 是由为启用了音频会议的每个 Skype for Business 用户创建的号码所创建的代码。 音频会议 PIN 由会议组织者用来标识他们是会议组织者并允许他们通过电话启动会议。 如果他们使用 Skype for Business 应用启动会议，则不需要 PIN。 如果用户忘记了 PIN，在启用音频会议时发送给他们的电子邮件中找不到 PIN，则管理员可以重置其 PIN，也可以重置自己的 PIN。
  
当经过身份验证的用户使用 Skype for Business 应用加入或者组织者通过电话使用其 PIN 加入时，可以开始会议。 如果会议要求提供 PIN 才能启动，则通过电话加入会议的所有用户都将进入会议厅并将收听保持音乐，直至会议启动。 如果会议组织者不需要 PIN 来通过电话启动会议，则当呼叫者加入会议时，系统不会要求他们提供 PIN。
  
## <a name="reset-a-users-pin"></a>重置用户的 PIN

1. 使用工作或学校帐户登录。
    
2. 转到 Skype **for Business**>管理中心，在左侧导航中，单击"**音频会议"。**
    
3. 单击 **"用户**"，选择要重置 PIN 的用户。
    
4. 在"操作"窗格中的 **"PIN"下**，单击"**重置"。**
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>让用户重置其自己的 PIN

用户可以使用"电话拨入式会议"页面上的"重置 **PIN"****选项重置 PIN。** 可通过以下三种方式之一访问此页面：

* 在浏览器中，转到 [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling) 。
* 在 Skype for Business 中，单击"选项"旁边的"显示 **菜单**"**箭头，然后单击**"工具  >  **""电话拨入式会议设置"。**
* 在 Skype for Business 中，单击"**选项**"，**单击左侧** 菜单中的"呼叫转发"，然后在"更多呼叫 **设置**"部分中，单击"**联机编辑设置"。** 

## <a name="what-else-should-you-know-about-pins"></a>你还应该知道有关 PIN 的哪些信息？

- 出于安全考虑，PIN 仅在重置时向管理员显示一次。 管理员重置 PIN 后，PIN 将在 **Skype for Business** 管理中心列出为 **************，当他们在 skype for Business 管理中心中使用Get-CsCsOnlineDialInConfencingUser时Windows PowerShell。
    
- 默认情况下，会自动向用户发送电子邮件，并且当用户启用音频会议或重置 PIN 时，将收到一封包含其 PIN 的电子邮件。 但是，如果已禁用自动发送电子邮件，则 PIN 重置电子邮件不会发送给用户，您必须手动将 PIN 信息发送给用户。
    
- 当会议启动时，会议厅中的所有用户都将自动加入该会议。 例如，如果两个参与者在会议启动之前尝试加入会议，他们将进入会议厅并将收听保持音乐，当会议组织者通过电话使用 PIN 加入时，该会议将启动，会议厅中的参与者将加入会议。
    
- 默认设置是不允许匿名呼叫者启动会议。
    
- 当你为用户启用音频会议时，默认情况下会向用户发送包含会议信息和 PIN 的电子邮件。 用户必须具有 Microsoft 365 或 Office 365 邮箱，因为重置 PIN 时，将在电子邮件中向用户发送新的 PIN，并发送到用户设置的主要 SMTP 地址 (别名) 。
    
- 设置音频会议时，设置组织中 PIN 所需的数字。 PIN 可以包含 4 至 12 个数字，默认情况下为 5 个。 如果更改 PIN 长度设置，该设置将仅应用于新生成的 PIN，不会应用于为音频会议启用的现有用户的 PIN 设置。 请参阅 [设置音频会议 PIN 的长度](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)。
    
- 默认情况下，电子邮件将设置为用户的 Microsoft 365 或 Office 365 主 SMTP 地址。 您可以向非 Microsoft 365 或非 Office 365 地址（如 Hotmail 或 MSN 电子邮件地址）发送电子邮件。 可以使用默认电子邮件地址替代Windows PowerShell。 如果用户在 Microsoft 365 或 Office 365 中没有 Exchange 邮箱，此功能非常有用。
    
- 若要覆盖发送电子邮件的默认用户地址，租户管理员可以使用以下 cmdlet：Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com"。 SendEmail 参数是替代用户电子邮件地址的必需参数。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet。
    
- 你可以通过运行以下命令来设置 Amos Marble 的 PIN：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365，当您有多个任务需要执行时，可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为何需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell比使用 Microsoft 365 管理中心具有许多速度、简单性和工作效率优势，例如，一次为许多用户更改设置时。 请在以下主题中了解这些优点：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)