---
title: 通过电话在 Skype for Business Online 开始音频会议而无 PIN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: '了解如何启用或禁用从 Skype for Business Online 管理中心或使用 PowerShell 脚本参加会议的匿名呼叫者。 '
ms.openlocfilehash: a87fe66eca889e7424ed34376dbf499f8bbfef81
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885158"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>通过电话在 Skype for Business Online 开始音频会议而无 PIN

> [!Note]
> 有关在 Microsoft Teams 无 PIN 启动音频会议的信息，请参阅[通过电话在 Microsoft Teams 中无 PIN 开始音频会议](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)。

可能会干扰拨入会议以将其保留在收听音乐，因为业务会议组织者的 Skype 尚未启动会议的会议的会议厅中的用户。 
  
如果会议组织者在调用会议，默认情况下，启动会议需要 PIN。 您可以将它设置以便任何人都可以拨号加入会议并不会提示输入 PIN 才能启动会议。 你可以使用 Skype for Business 管理中心为单个用户启用或禁用此设置。
  
PIN 不需要会议组织者，如果某人已从业务应用程序 Skype 开始会议。 只有当会议组织者通过电话加入会议时，才需要 PIN。 已分配的**音频会议**许可证并启用了音频会议时，将向音频用户发送会议的 PIN。 请参阅[发送对其进行音频会议信息的用户电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)和[自动发送给其音频会议设置更改时的用户的电子邮件](emails-sent-to-users-when-their-settings-change.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>启用或禁用匿名呼叫者加入会议
    
1. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **用户**。 
    
2. 在列表中，选择用户，然后在操作窗格中，单击**编辑**。 
    
3. 在用户的属性页上，在**会议选项**中，选中或清除**允许未经身份验证的呼叫者在会议中的第一个人。如果不需要，然后他们将在会议厅中等待直至经过身份验证的用户加入**。
    
4. 单击" **保存**"。 


    
 **使用 Windows Powershell**
  
- 请运行以下命令： 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>你还需了解哪些信息？

- 如果您想要重置 PIN，请参阅[重置的音频会议 PIN](reset-the-audio-conferencing-pin.md)。
    
- 如果启用了匿名访问，或不需要 PIN 才能启动会议时，:
    
  - 如果尚未启动会议 （没有一种-会议尚未）： 将提示呼叫者，如果他是组织者;如果他说是时，他将提示您为其 PIN，他输入 PIN 之后，会议的开始和用户将加入会议。
    
  - 如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。
    
- 如果禁用匿名访问，或不需要 PIN 才能开始会议，则：
    
  - 如果尚未启动会议（还没有会议）：如果呼叫者是组织者，将不会收到提示，并且从不提示她提供 PIN。 组织者的设置设置为关闭，因为会议将启动，匿名呼叫者将加入会议。
    
  - 如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或为多个用户自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet。
    
-  对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。使用 Windows PowerShell，可以通过单点管理来管理 Office 365，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
