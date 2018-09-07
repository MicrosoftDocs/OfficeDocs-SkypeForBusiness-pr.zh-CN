---
title: 在 Skype for Business Online 中重置用户的会议 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: '了解在 Skype for Business Online 中重置用户会议 ID 的步骤，并获取会议更新和迁移工具的链接。 '
ms.openlocfilehash: 34e165d92f4dc63eea8fc31c05612b6e20b64025
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850058"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>在 Skype for Business Online 中重置用户的会议 ID

> [!NOTE]
> 有关重置 Microsoft Teams 中的会议 ID 的信息，请参阅[在 Microsoft  Teams 中重置用户的会议 ID](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)。

会议邀请底部包含有动态会议 ID，以及呼叫者可用于拨入会议的电话号码。 用户拨打该电话号码时，会议的自动助理会要求呼叫者输入此会议 ID 方可参加会议。
  
> [!NOTE]
> 如果你的会议提供商是 Microsoft，默认情况下用户的会议 ID 设置为“仅动态”。 但是，不能在 Skype for Business 管理中心或使用 Windows Powershell 将其更改为静态，目前该操作不受支持。 仅为启用音频会议的 Skype for Business 用户自动设置会议 ID。 

## <a name="resetting-the-conference-id-for-a-user"></a>重置用户的会议 ID
   
1. 在 **Skype for Business 管理中心**，单击**音频会议** > **用户**，选择用户，然后在**会议 ID** 下的操作窗格中单击**重置**。
    
2. 在**重置会议 ID？** 窗口，单击**是**。 会议 ID 将自动创建，将有一封含有新会议 ID 的电子邮件发送给用户。 默认情况下，电子邮件会发送给用户，但这一功能可以关闭。
    
> [!NOTE]
> [!注释] 重置会议 ID 后，会向用户发送包含新会议 ID 的电子邮件。此电子邮件将发送到主电子邮件地址，大多数情况下是其 Office 365 邮箱。电子邮件中包含新的会议 ID、默认拨入电话号码以及使用 Skype for Business 会议更新工具更新现有会议的说明。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>我还需了解哪些信息？

- 你可以单击 **通过电子邮件发送会议信息**，在一封电子邮件中向“操作”窗 格中的用户发送全部会议信息，包括会议 ID 和拨入电话号码。 它不会发送 PIN。
    
- 会议 ID 必须包含 7 位数，不能在 Skype for Business 管理中心中或使用 Windows PowerShell 更改其长度。
    
- 重置之后，你可以看到新会议 ID 列在**会议 ID** 下方。
    
- 当你在**用户**页面上选择用户时，可以在“操作”窗格底部的**音频会议**下查看用户的音频会议 ID。
    
- 创建新会议 ID 后，呼叫者不能再使用旧会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 用户可以使用 Skype for Business 会议工具来更新其现有会议。 要了解如何下载、安装和运行 Skype for Business 会议更新工具，请参阅：
    
  - [Skype for Business 和 Lync 的会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online、会议迁移工具（64 位）](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online、会议迁移工具（32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题

[重置音频会议 PIN](reset-the-audio-conferencing-pin.md)
