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
description: '了解有关引脚以及如何在 Skype for Business Online 中重置它们的信息。 '
ms.openlocfilehash: fdd11e3ef9c656b4b2cc6b929a2963e9b5e10824
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680559"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>在 Skype for Business Online 中重置音频会议 PIN

> [!Note]
> 有关在 Microsoft 团队中重置音频会议 pin 的信息，请参阅[重置 Microsoft 团队中的音频会议 pin](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)。

PIN 是由为每个启用了音频会议的 Skype for business 用户创建的数字组成的代码。 会议组织者使用音频会议 Pin 标识他们是会议组织者，并允许他们通过电话启动会议。 如果他们使用 Skype for Business 应用启动会议，则不需要 PIN 码。 如果用户忘记了 PIN，并且他们在启用音频会议时收到的电子邮件中找不到该用户的 PIN，则管理员可以重置其 PIN，也可以重置其自己的 PIN。
  
当通过身份验证的用户使用 Skype for Business 应用加入或当组织者通过电话与他或她的 PIN 进行联接时，可以启动会议。 如果会议要求提供 PIN 才能启动，则通过电话加入会议的所有用户都将进入会议厅并将收听保持音乐，直至会议启动。 如果会议组织者不需要 PIN 来通过电话启动会议，则当呼叫者加入会议时，系统不会要求他们提供 PIN。
  
## <a name="reset-a-users-pin"></a>重置用户的 PIN

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到管理中心 > **Skype for**business，然后在左侧导航中单击 "**音频会议**"。
    
3. 单击 "**用户**"，选择要为其重置 PIN 的用户。
    
4. 在操作窗格中的 "**固定**" 下，单击 "**重置**"。
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>让用户重置其自己的 PIN

用户可以通过使用 "**电话拨入式会议**" 页面上的 "**重置 pin** " 选项重置 pin。 可通过以下三种方式之一访问此页面：

* 在浏览器中，转[https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling)到。
* 在 Skype for business 中，单击 "**选项**" 旁边的 "**显示菜单**" 箭头，然后单击 "**工具** > **电话拨入式会议设置**"。
* 在 Skype for Business 中，单击 "**选项**"，在左侧菜单中单击 "**呼叫转接**"，然后在 "**更多通话设置**" 部分中，单击 "**编辑联机设置**"。 

## <a name="what-else-should-you-know-about-pins"></a>你还应该知道有关 PIN 的哪些信息？

- 出于安全考虑，PIN 仅在重置时向管理员显示一次。 在管理员重置 PIN 后，在 Skype for Business 管理中心以及在 Windows PowerShell 中使用 CsCsOnlineDialInConfencingUser 时，PIN 将在**Skype For business 管理中心**和结果中列为 * * * * * * *。
    
- 默认情况下启用 "自动向用户发送电子邮件"，用户在启用音频会议或 PIN 重置时，将收到一封电子邮件及其 PIN。 但是，如果您已禁用自动发送电子邮件，则 PIN 重置电子邮件不会发送给用户，您将必须手动向用户发送 PIN 信息。
    
- 当会议启动时，会议厅中的所有用户都将自动加入该会议。 例如，如果两个参与者在会议启动之前尝试加入会议，他们将进入会议厅并将收听保持音乐，当会议组织者通过电话使用 PIN 加入时，该会议将启动，会议厅中的参与者将加入会议。
    
- 默认设置是不允许匿名呼叫者启动会议。
    
- 当为用户启用音频会议时，默认情况下，会向他们发送包含会议信息的电子邮件及其 PIN 码。 用户必须拥有 Office 365 邮箱，因为当重置 PIN 时，将向用户发送电子邮件中的新 PIN，以发送到为用户设置的主 SMTP 地址（别名）。
    
- 设置音频会议时，设置您的组织中的 Pin 所需的数字。 PIN 可以包含 4 至 12 个数字，默认情况下为 5 个。 如果您更改了 "引脚长度" 设置，则该设置仅应用于新生成的引脚，并且不会应用到已启用音频会议的现有用户的引脚设置。 请参阅[设置音频会议会议的 PIN 长度](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)。
    
- 默认情况下，电子邮件将设置为用户的 Office 365 主 SMTP 地址。 您可以向非 Office 365 地址（如 Hotmail 或 MSN 电子邮件地址）发送电子邮件。 你可以使用 Windows PowerShell 替代默认电子邮件地址。 如果用户在 Office 365 中没有 Exchange 邮箱，则此功能非常有用。
    
- 若要覆盖发送电子邮件的默认用户地址，租户管理员可以使用以下 cmdlet： Get-csonlinedialinconferencinguser-amos-ResetLeaderPIN-SendEmail-SendEmailToAddress "u@hotmail.com"。 需要使用 SendEmail 参数来替代用户的电子邮件地址。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet。
    
- 你可以通过运行以下命令来设置 Amos Marble 的 PIN：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你在一次为多个用户进行设置更改时。 请在以下主题中了解这些优点：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)
