---
title: 在 Microsoft Teams 中重置用户的会议 ID
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解在 Microsoft Teams 中重置用户的会议 ID 以及获取会议更新和迁移工具链接的步骤。 '
ms.openlocfilehash: 4e338e5ad00792a48e0a6c9e0791c0c5e4b759ac
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887849"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>在 Microsoft Teams 中重置用户的会议 ID

一个动态会议 ID 与呼叫者可用于拨入会议的拨入电话号码一起包含在会议邀请底部。 在用户拨打电话号码时，会议的自动助理会要求呼叫者输入此会议 ID 才能参加会议。
  
> [!NOTE]
> 如果你的会议提供商是 Microsoft，则默认情况下，你的用户的会议 ID 设置为“仅动态”。 很遗憾，无法将其更改为静态，因为现在不支持。 仅会为启用了音频会议的 Microsoft Teams 用户自动设置会议 ID。 


## <a name="resetting-the-conference-id-for-a-user"></a>重置用户的会议 ID

1. 在左侧导航中，单击“**用户**”，然后从可用用户列表中选择用户。

2. 在页面顶部，单击“**编辑**”。

3. 在“**音频会议**”下，单击“**重置会议 ID**”。

2. 在“**重置会议 ID**”窗口中，单击“**重置**”。 将自动创建一个会议 ID，并向用户发送包含新会议 ID 的电子邮件。 默认情况下，将向用户发送电子邮件，但可以关闭此功能。   

    
> [!NOTE]
> 重置会议 ID 后，将向用户发送包含新会议 ID 的电子邮件。 此电子邮件将发送到主电子邮件地址，大多数情况下是其 Office 365 邮箱。 该电子邮件包含新会议 ID、默认拨入电话号码以及更新现有会议的说明。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>我还应该了解哪些信息？

- 你可以在“**音频会议**”部分针对用户单击“**通过电子邮件发送会议信息**”，通过电子邮件向用户发送所有会议信息（包括会议 ID 和拨入电话号码）。 它不会发送 PIN。
    
- 会议 ID 将包含 7 位数，你不能更改其长度。
    
- 重置后，你可以看到新会议 ID 列在“**会议 ID**”下。
    
- 创建新会议 ID 后，呼叫者不能使用旧会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。
    
## <a name="related-topics"></a>相关主题

[重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)
