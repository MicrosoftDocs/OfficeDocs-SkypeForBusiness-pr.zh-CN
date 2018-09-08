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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解如何启用或禁用从 Skype for Business Online 管理中心或使用 PowerShell 脚本参加会议的匿名呼叫者。 '
ms.openlocfilehash: 746e21b7b1a8d15c31dfe11e46ac09edfbb29b99
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858702"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>通过电话在 Skype for Business Online 开始音频会议而无 PIN

> [!Note]
> 有关在 Microsoft Teams 无 PIN 启动音频会议的信息，请参阅[通过电话在 Microsoft Teams 中无 PIN 开始音频会议](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)。

对于用户来说，拨入要在会议厅举行的会议但只能听音乐等候可能会感到沮丧，因为组织者尚未启动会议。 
  
如果会议组织者拨入会议，默认情况下，需要 PIN 才能启动会议。 您可以对其进行设置，以便所有人都可以拨入会议，而不提示他们输入 PIN 来启动会议。 您可以使用 Skype for Business 管理中心为单个用户启用或禁用此设置。
  
如果某人已从 Skype for Business 开始会议，则会议组织者无需 PIN。PIN 仅在会议组织者通过电话加入会议时必需。当分配有**音频会议** 许可证并启用了音频会议时，将向音频用户发送会议的 PIN。请参阅 [发送带音频会议信息的电子邮件给用户](send-an-email-to-a-user-with-their-dial-in-information.md)和[音频会议设置更改时自动发送给用户的电子邮件](emails-sent-to-users-when-their-settings-change.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>启用或禁用匿名呼叫者加入会议
    
1. 在左侧导航的 **Skype for Business 管理中心**中，转到**音频会议** >  **用户** 。 
    
2. 在列表中，选择用户，并单击“操作”窗格中的**编辑**。 
    
3. 在用户的属性页面，**会议选项**下，选中或取消选中**允许未经身份验证的呼叫者成为第一个参加会议的人。 如果不允许，他们将在大厅中等待，直到有经过身份验证的用户加入**。
    
4. 单击**保存**。 


    
 **使用 Windows PowerShell**
  
- 请运行以下： 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>您还需了解哪些信息？

- 如果要重置 PIN，请参阅[重置音频会议 PIN](reset-the-audio-conferencing-pin.md)。
    
- 如果已启用匿名访问或不要求使用 PIN 来启动会议：
    
  - 如果尚未启动会议（还没有会议）：将提示呼叫者是否是组织者；如果他说是，则提示他输入 PIN；输入 PIN 后，会议开始，用户将加入会议。
    
  - 如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。
    
- 如果已禁用匿名访问或不要求使用 PIN 来启动会议：
    
  - 如果尚未启动会议（还没有会议）：如果呼叫者是组织者，将不会收到提示，并且从不提示她提供 PIN。 由于组织者的设置设定为禁用，该会议将启动，匿名呼叫者将加入会议。
    
  - 如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或为多个用户自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet。
    
-  对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。使用 Windows PowerShell，可以通过单点管理来管理 Office 365，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 在速度、简单性和生产率方面有许多优点，仅限于使用 Office 365 管理中心，例如当您同时为许多用户进行设置更改时。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
