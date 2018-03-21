---
title: "开始音频会议通过 PIN 没有电话"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: 09bd10890728c321b989003cc94b14b5143fb2da
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2018
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a>开始音频会议通过 PIN 没有电话

它可能是令人沮丧的用户拨入的在会议厅中听音乐，因为 Skype 的业务或 Microsoft 小组会议的组织者尚未启动会议召开的会议。 
  
如果会议组织者调用参加会议时，默认情况下，启动会议需要一个 PIN。 您可以设置它，以便任何人都可以拨号加入会议并不会提示输入 PIN 开始举行会议。 你可以使用 Skype for Business 管理中心为单个用户启用或禁用此设置。
  
PIN 不需为会议组织者，如果有人从 Skype 业务或 Microsoft 小组应用程序的启动会议。 只有当会议组织者通过电话加入会议时，才需要 PIN。 当它们被分配**音频会议**许可并启用了音频会议会议的引出发给音频的用户。 请参阅[发送给用户，并他们的音频会议信息的电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)和[电子邮件自动发送给用户的音频会议设置更改时](emails-sent-to-users-when-their-settings-change.md)。
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>启用或禁用匿名呼叫者加入会议

1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **用户**。 
    
4. 在列表中，选择该用户并在操作窗格中单击**编辑**。 
    
5. 在用户的属性页，在**会议选项**中，选中或清除**允许未经身份验证的调用方将在会议中的第一人。如果不是，然后他们将等到在休息室已经过身份验证的用户加入**。
    
6. 单击" **保存**"。 
    
 **若要启用或禁用对所有用户的会议使用 Windows Powershell 的匿名呼叫者**
  
- 请运行以下命令： 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>你还需了解哪些信息？

- 如果要重置 PIN，请参阅[重置用户的音频会议 PIN](reset-the-audio-conferencing-pin-for-a-user.md)。
    
- 如果启用了匿名访问，或如果不要求 PIN 来召开会议：
    
  - 如果尚未启动会议 （没有任何人在会议中尚未）： 呼叫者将会提示您，如果他是组织者;如果他说是，他将会提示您为自己的 PIN，并他输入 PIN 后，会议将开始用户将加入会议。
    
  - 如果此时会议已启动 （其他人已在会议中）： 呼叫者不会提示，如果他是组织者，他将永远不会被提示针;此时会议已启动，并调用方将加入它。
    
- 如果禁用匿名访问，或如果不要求 PIN 来召开会议时，则：
    
  - 如果尚未启动会议 （没有任何人在会议中尚未）： 如果她是组织者，而且她将永远不会提示您输入 PIN，将不提示调用方。 管理器的设置被设置为 off，因为会议的开始和匿名呼叫者将参加会议。
    
  - 如果此时会议已启动 （其他人已在会议中）： 呼叫者将不会提示您，如果她是组织者，而且她将永远不会提示您输入 PIN，; 此时会议已启动，并调用方将加入它。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或为多个用户自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet。
    
-  对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。 使用 Windows PowerShell，可以通过单点管理来管理 Office 365，这样做可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 许多相比具有的优势在速度、 简易性和生产率仅使用 Office 365 管理中心，例如当您所更改的设置对于许多用户一次。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[设置音频会议 for Skype Business 和 Microsoft 团队](set-up-audio-conferencing.md)
