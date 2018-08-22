---
title: 对业务 Online 重置 Skype 中的用户的会议 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: '了解重置用户的步骤的业务 online，会议中 Skype 的会议 ID 和获取链接到会议更新和迁移工具。 '
ms.openlocfilehash: ac37d682d45b22eff61392ee05d7c369d67c3b67
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490532"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>对业务 Online 重置 Skype 中的用户的会议 ID

> [!NOTE]
> 有关重置 Microsoft 团队中的会议 ID 的信息，请参阅[重置 Microsoft 团队中的用户的会议 ID](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)。

底部的会议邀请以及的拨入电话号码的呼叫者可用于向会议呼叫中包含动态的会议 ID。 当用户拨打的电话号码时，会议自动助理会要求呼叫者输入此会议 ID，以便他们可以参加会议。
  
> [!NOTE]
> 如果您的会议提供商是 Microsoft，默认情况下用户的会议 Id 设置为仅动态中。 遗憾的是，它不能更改业务管理中心或使用 Windows Powershell 成为静态的因为这是现在 Skype 中不受支持。 仅为启用音频会议的企业用户的 Skype 自动设置会议 Id。 

## <a name="resetting-the-conference-id-for-a-user"></a>重置用户的会议 ID
   
1. 中的**Skype 业务管理中心的**中，单击**音频会议** > **用户**，选择一个用户，，，然后单击下**的会议 ID**操作窗格中的**重置**。
    
2. 在**重置的会议 ID？** 窗口中，单击**是**。 A conference ID will be automatically created and an email sent to the user with the new conference ID. 默认情况下电子邮件发送给用户，但这可以关闭。
    
> [!NOTE]
> [!注释] 重置会议 ID 后，会向用户发送包含新会议 ID 的电子邮件。此电子邮件将发送到主电子邮件地址，大多数情况下是其 Office 365 邮箱。电子邮件中包含新的会议 ID、默认拨入电话号码以及使用 Skype for Business 会议更新工具更新现有会议的说明。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>我还需了解哪些信息？

- 您可以向中包括会议 ID 和电话拨入电话号码，通过单击**发送电子邮件的会议信息**的操作窗格中的用户的电子邮件的用户发送的所有会议信息。 它不会发送 PIN。
    
- 会议 ID 将包含 7 位数字，并且您无法更改它 Skype 业务管理中心或使用 Windows PowerShell 中的长度。
    
- 重置之后，你可以看到新会议 ID 列在" **会议 ID**"下方。
    
- 如果您选择**用户**页上的用户可以查看为音频会议用户的会议 ID 底部的操作窗格下**音频会议**。
    
- 创建新会议 ID 后，呼叫者不能再使用旧会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 用户可以使用 Skype 业务会议工具更新其现有会议。 若要查看如何下载、 安装和运行 Skype 业务会议更新工具，请参阅：
    
  - [Skype for Business 和 Lync 的会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online、会议迁移工具（64 位）](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online、会议迁移工具（32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么您需要使用 Office 365 PowerShell 中](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题

[重置 PIN 的音频会议](reset-the-audio-conferencing-pin.md)
